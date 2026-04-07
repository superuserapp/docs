# Managing tools

You can manage your tools directly via their page in the package registry. We'll use the [Superuser: Weather by Open-Meteo](https://superuser.app/org/superuser/toolkits/open-meteo) as an example, available at [https://superuser.app/org/superuser/toolkits/open-meteo](https://superuser.app/org/superuser/toolkits/open-meteo).

## Change name and description

<figure><img src="../../.gitbook/assets/SCR-20260407-csew.png" alt=""><figcaption></figcaption></figure>

To change the name and description of your tool, once it's published just click the edit button next to the name or description.

## View endpoint (and code)

Every tool in a package is just an API endpoint, because Superuser tool packages are just APIs hosted on serverless infrastructure. To view an endpoint and see information about it — like description, parameters, etc. — just click on it in the endpoints list.

{% hint style="warning" %}
Only **open source** packages will show endpoint code. Public and private packages will not show code.
{% endhint %}

<figure><img src="../../.gitbook/assets/SCR-20260407-cugw.png" alt=""><figcaption></figcaption></figure>

Once you've selected the endpoint, you'll be able to see more details:

<figure><img src="../../.gitbook/assets/SCR-20260407-cuma.png" alt=""><figcaption></figcaption></figure>

* Endpoint pathname and description
* Arguments

<figure><img src="../../.gitbook/assets/SCR-20260407-cutu.png" alt=""><figcaption></figcaption></figure>

* Endpoint code (if applicable)

<figure><img src="../../.gitbook/assets/SCR-20260407-cvku.png" alt=""><figcaption></figcaption></figure>

* Usage example (how to cURL or execute via Node.js)
* Request parameters (TypeScript or JSON Schema)
