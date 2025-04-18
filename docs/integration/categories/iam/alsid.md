uuid: 44d41a2b-96cb-4d37-84e0-4f0c0f9138b8
name: Tenable Identity Exposure / Alsid
type: intake

## Overview
Tenable Identity Exposure / Alsid is an automated security solution that monitors the components of Active Directory infrastructures by detecting attacks in real time, identifying existing weaknesses and vulnerabilities.

- **Vendor**: Tenable Identity Exposure / Alsid
- **Supported environment**: On prem
- **Detection based on**: Alert, Telemetry
- **Supported application or feature**:Application logs, Authentication logs, Network protocol analysis





## Configure

As of now, the main solution to collect Tenable Identity Exposure / Alsid logs leverages the Rsyslog recipe. Please share your experiences with other recipes by editing this documentation.

### Rsyslog

Please refer to the documentation of Tenable Identity Exposure / Alsid to forward events to your rsyslog server. The reader is also invited to consult the [Rsyslog Transport](/integration/ingestion_methods/syslog/overview.md) documentation to forward these logs to Sekoia.io.

{!_shared_content/integration/detection_section.md!}

{!_shared_content/operations_center/detection/generated/suggested_rules_44d41a2b-96cb-4d37-84e0-4f0c0f9138b8_do_not_edit_manually.md!}
{!_shared_content/operations_center/integrations/generated/44d41a2b-96cb-4d37-84e0-4f0c0f9138b8.md!}

