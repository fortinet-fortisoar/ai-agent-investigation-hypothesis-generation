# Release Information

- **Version**: 1.0.0

- **Certified**: Yes

- **Publisher**: Fortinet

- **Scope**: Analysis and Investigation

- **Verified with Models**: Fortinet FortiAI (AI model Large)

# Investigation Hypothesis Generation Agent

Generates investigation hypotheses for security alerts or incidents based on observed indicators, behaviors, and contextual data.

## Installation

This agent installs along with the FortiAI solution pack.

## Configuration

**Required MCP Servers**: NA

<!-- > [!Note]
>
> Refer to [Configuring MCP Servers](https://docs.fortinet.com/document/fortisoar/8.0.0/administration-guide/823139/mcp-servers#Configure_MCP_Servers) on FortiSOAR platform documentation for information on configuring a custom MCP server.
>  -->

### Prerequisites

- The FortiAI solution pack must be installed and configured with the Fortinet FortiAI connector.

  - To configure the FortiAI solution pack, refer to the [FortiAI](https://github.com/fortinet-fortisoar/solution-pack-fortinet-advisor/) solution pack documentation.
  - To configure the Fortinet FortiAI connector, refer to the [Fortinet FortiAI](https://docs.fortinet.com/fortisoar/connectors/fortinet-fortiai) connector documentation.

> [!Note]
>
> FortiAI solution pack and Fortinet FortiAI connector are preconfigured out-of-the-box with FortiSOAR `v8.0.0`.
> 


## Input Parameters

The input must be provided as a JSON object.

| Parameter    | Description                                                                                                            |
|--------------|------------------------------------------------------------------------------------------------------------------------|
| `context`    | Raw alert data used as the primary context for hypothesis generation. This represents the unprocessed alert payload.   |
| `indicators` | A list or object containing extracted indicators (e.g., IPs, domains, hashes, users, processes) relevant to the alert. |

## Response

The output is returned as a JSON object.

| Parameter           | Description                                                                |
|---------------------|----------------------------------------------------------------------------|
| `id`                | Unique identifier containing only numbers                                  |
| `name`              | Name of the detected threat or entity                                      |
| `intent`            | Classification of intent: BENIGN, MALICIOUS, FALSE POSITIVE, or SUSPICIOUS |
| `explanatory_focus` | Primary focus area of the threat analysis                                  |
| `description`       | Detailed description of the threat or finding                              |
| `reasoning`         | Explanation of the analysis                                                |
| `tactics`           | Array of MITRE ATT&CK tactics associated with the threat                   |
| `techniques`        | Array of MITRE ATT&CK techniques used in the threat                        |

