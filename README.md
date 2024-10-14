
# QuickSkope

**QuickSkope** is a proof-of-concept (POC) Python script designed to streamline the process of obtaining a user's configuration file from Netskope. By providing the user’s tenant name and a valid email address, QuickSkope automates the retrieval and download of the configuration file, saving it locally as `nsbranding.json` upon success.

More information on the research we did to investigate this: [https://quickskope.com/vulnerability/research/2024/10/14/Quick-Skoping.html](https://quickskope.com/vulnerability/research/2024/10/14/Quick-Skoping.html)

## Disclaimer:
This Python script is intended for educational purposes only. It demonstrates a proof of concept for automating the retrieval of user configuration files using the CVE-2024-7401 vulnerability. Please use this script responsibly and only on systems you are authorized to test. Unauthorized or malicious use is strictly prohibited.

## Features

- Automates the retrieval of a user's configuration file using their tenant name and email address.
- Downloads the configuration file and saves it as `nsbranding.json`.

## Requirements

Before running QuickSkope, ensure you have the following installed:

- Python 3.x

## Installation

1. Clone this repository to your local machine:
    ```
    git clone https://github.com/yourusername/QuickSkope.git
    cd Quickskope
    python quick-scope.py help
    Commands:
      validate <tenant_name>              - Validates a Netskope tenant name and prints the OrgKey.
      config <tenant_name> <email>        - Exports a manipulated config for you to use with the Netskope client.
      download <tenant_name> <win/mac>    - Downloads the Netskope client for you to install.
      help                                - Displays this help menu.
      no-banner                           - Suppresses the ASCII banner.
    ```

## Usage

To use QuickSkope, provide the tenant name and a valid email address:

```
python quickskope.py validate <tenant-name>
```

### Example:

```
python quick-skope.py config <tenant_name> <email>
```

Once executed, the script will:

1. Validate the provided email address.
2. Attempt to retrieve the user’s configuration file.
3. If successful, save the file as `nsbranding.json` in the current directory.


## Output

- If successful, the script will download the user’s configuration file and save it as `nsbranding.json`.
- If the retrieval fails, the script will display an error message detailing the issue.

## Troubleshooting

- Ensure that the provided tenant name and email address are correct.
- Verify that you have a working internet connection and access to the necessary API endpoints.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Credit
- 0xDisrel: Helping me write the proof of concept and working with me on the research: [https://x.com/0xDISREL](https://x.com/0xDISREL)
- Sander Di Wit: Uncovering the Orginal Vulnerability to NetSkope

## References

NetSkope Documentation: 
- Configuring Netskope Tenants: [https://docs.netskope.com/en/configure-netskope-tenants/](https://docs.netskope.com/en/configure-netskope-tenants/)
- Overview of Netskope Client: [https://docs.netskope.com/en/netskope-client-overview/](https://docs.netskope.com/en/netskope-client-overview/)
- Netskope Client Configuration: [https://docs.netskope.com/en/netskope-client-network-configuration/](https://docs.netskope.com/en/netskope-client-network-configuration/)
- Netskope Client Command Refence: [https://docs.netskope.com/en/netskope-client-command-reference/](https://docs.netskope.com/en/netskope-client-command-reference/)
- Netskope Secure Enrollment: [https://docs.netskope.com/en/secure-enrollment/](https://docs.netskope.com/en/secure-enrollment/)

CVE References: 
- [https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2024-7401](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2024-7401)
- [https://www.cve.org/CVERecord?id=CVE-2024-7401](https://www.cve.org/CVERecord?id=CVE-2024-7401)
- [https://www.netskope.com/company/security-compliance-and-assurance/security-advisories-and-disclosures/netskope-security-advisory-nskpsa-2024-001](https://www.netskope.com/company/security-compliance-and-assurance/security-advisories-and-disclosures/netskope-security-advisory-nskpsa-2024-001)
