# What is a wildcard certificate?

A wildcard certificate is a type of SSL/TLS certificate that is designed to secure multiple subdomains of a single domain with a single certificate. Instead of specifying individual subdomains in the certificate, you can use a wildcard character (*) to represent multiple subdomains. The asterisk (*) is typically used as the wildcard character.

For example, if you have a wildcard certificate for `*.example.com`, it can secure:

1. `www.example.com`
2. `mail.example.com`
3. `blog.example.com`
4. Any other subdomain of `example.com`

Wildcard certificates provide flexibility and cost-efficiency for organizations that have numerous subdomains under a single domain because you don't need to purchase and manage individual certificates for each subdomain. However, it's essential to be cautious when using wildcard certificates, as they can potentially pose security risks if not properly managed. If the private key for a wildcard certificate is compromised, an attacker could use it to secure malicious subdomains under the same domain.

In summary, a wildcard certificate is a convenient way to secure multiple subdomains under a single domain with a single certificate, using a wildcard character (*) to represent the variable subdomain names.