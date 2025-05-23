uuid: 0642b03a-9d4a-4c88-a5e2-4597e366b8c4
name: VMWare VCenter
type: intake

## Overview
- **Vendor**:
- **Supported environment**:
- **Version compatibility**:
- **Detection based on**: Telemetry
- **Supported application or feature**:

VMWare VCenter is a centralized management software. It provides a single point of control for managing virtual machines and ESXi hosts from a centralized interface.



## Configure

### Prerequisites

An internal log concentrator is required to collect and forward events to Sekoia.io.

### Enable Syslog forwarding

- Log in to the vCenter Server Management, with the administrative rights
- On the left panel, click `Syslog`
- In the Forwarding configuration, create a new configuration by clicking `CONFIGURE` or edit an existing one by clicking `EDIT`
- Click `+ ADD` to create an additional remote servers (up to 3) in the configuration if one already exists
- Type the ip address, the port of the log concentrator and select the protocol (we recommend TCP)
- Click `SAVE`
- Click `SEND TEST MESSAGE` to validate the status of the connection.

## Create the intake

Go to the [intake page](https://app.sekoia.io/operations/intakes) and create a new intake from the format `VMWare VCenter`.

## Forward logs to Sekoia.io

Please consult the [Syslog Forwarding](/integration/ingestion_methods/syslog/sekoiaio_forwarder.md) documentation to forward these logs to Sekoia.io.

Create a new configuration file:

```
sudo vim ./extended_conf/11-vcenter.conf
```

with the following template:

```
input(type="imtcp" port="PORT" ruleset="remoteVmwarevCenter")

template(name="SEKOIAIOTemplate" type="string" string="<%pri%>1 %timestamp:::date-rfc3339% %hostname% %app-name% %procid% LOG [SEKOIA@53288 intake_key=\"YOUR_INTAKE_KEY\"] %msg%\n")
ruleset(name="remoteVmwarevCenter"){
  if($programname == "vpxd") then {
    action(
        type="omfwd"
        protocol="tcp"
        target="intake.sekoia.io"
        port="10514"
        TCP_Framing="octet-counted"
        StreamDriver="gtls"
        StreamDriverMode="1"
        StreamDriverAuthMode="x509/name"
        StreamDriverPermittedPeers="intake.sekoia.io"
        Template="SEKOIAIOTemplate"
    )
  }
}
```

!!! Note
    Please change using the `YOUR_INTAKE_KEY` accordingly, as well as, the `PORT`.

Update the `docker-compose.yml` file of the Sekoia.io forwarder to mount the extended conf:

```
volumes:
    - ./intakes.yaml:/intakes.yaml
...
    - ./extended_conf:/extended_conf
```

{!_shared_content/operations_center/integrations/generated/0642b03a-9d4a-4c88-a5e2-4597e366b8c4_sample.md!}


{!_shared_content/integration/detection_section.md!}

{!_shared_content/operations_center/detection/generated/suggested_rules_0642b03a-9d4a-4c88-a5e2-4597e366b8c4_do_not_edit_manually.md!}
{!_shared_content/operations_center/integrations/generated/0642b03a-9d4a-4c88-a5e2-4597e366b8c4.md!}

## Further Readings

- [Forward vCenter Server Log Files to Remote Syslog Server](https://docs.vmware.com/en/VMware-vSphere/7.0/com.vmware.vsphere.monitoring.doc/GUID-9633A961-A5C3-4658-B099-B81E0512DC21.html)
