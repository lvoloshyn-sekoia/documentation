uuid: c2faea65-1eb3-4f3f-b895-c8769a749d45
name: Fastly WAF Audit logs
type: intake


## Overview
- **Vendor**: Fastly
- **Supported environment**: SaaS
- **Detection based on**: Telemetry
- **Supported application or feature**: Web application firewall logs

Fastly WAF audit logs tracks activities related to your corp and your sites like user creation, rule creation, site configuration changes.



## Configure

### Creating API access tokens

1. Go to the [Fastly WAF](https://dashboard.signalsciences.net) and log in.
2. From the **My Profile** menu, select API access tokens.
3. Click **Add API access token**.
4. In the **Token name** field, enter a name to identify the access token.
5. Click **Create API access token**.
6. Record the token in a secure location for your use. Then, click **Continue** to finish creating the token.

!!! Warning
	This is the only time the token will be visible. Record the token and keep it secure.

### Sekoia.io configuration procedure

#### Create your intake

1. Go to the [intake page](https://app.sekoia.io/operations/intakes) and create a new intake from the `Fastly Audit`.
2. Enter `User's email`, `API token`, `Corporation name` and `Site name` (if needed) from the Fastly WAF dashboard



#### Enjoy your events on the [Events page](https://app.sekoia.io/operations/events)

{!_shared_content/operations_center/integrations/generated/c2faea65-1eb3-4f3f-b895-c8769a749d45_sample.md!}


{!_shared_content/integration/detection_section.md!}

{!_shared_content/operations_center/detection/generated/suggested_rules_c2faea65-1eb3-4f3f-b895-c8769a749d45_do_not_edit_manually.md!}
{!_shared_content/operations_center/integrations/generated/c2faea65-1eb3-4f3f-b895-c8769a749d45.md!}

