uuid: 46ca6fc8-3d30-434c-92ff-0e1cde564161
name: Proofpoint Targeted Attack Protection
type: intake

## Overview

Proofpoint Targeted Attack Protection (TAP) helps detect, mitigate, and block advanced threats that target people through email.

- **Vendor**: Proofpoint
- **Supported environment**: Cloud
- **Detection based on**: Telemetry
- **Supported application or feature**: Email gateway


## Configure

### Proofpoint Targeted Attack Protection

As a prerequisite, you need to create a service principal and a secret on the setting page:

- Sign in to the [dashboard](https://threatinsight.proofpoint.com/)
- Go to `Settings > Connected Applications`
- Click `Create New Credential`
- Type the name of the new credential set
- Generate the Service Principal and Secret values by clicking `Generate`


### Create the intake

1. Go to the [intake page](https://app.sekoia.io/operations/intakes) and create a new intake from the format `Proofpoint TAP`.
2. Set up the intake configuration with the service principal and the secret.

Start the playbook and enjoy your events.

{!_shared_content/operations_center/integrations/generated/46ca6fc8-3d30-434c-92ff-0e1cde564161_sample.md!}

{!_shared_content/integration/detection_section.md!}

{!_shared_content/operations_center/detection/generated/suggested_rules_46ca6fc8-3d30-434c-92ff-0e1cde564161_do_not_edit_manually.md!}

{!_shared_content/operations_center/integrations/generated/46ca6fc8-3d30-434c-92ff-0e1cde564161.md!}
