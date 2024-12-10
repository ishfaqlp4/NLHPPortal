html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Execute Function on Button Click</title>
</head>
<body>
  <button id="executeButton">Click Me</button>

  <script>
    const HPP_API_URL = `${window.location.origin}/${BPSystem?.organization}/hostedPayments/1.0`;

    const getHppSecurityToken = async () => {
      const requestUrl = `${HPP_API_URL}/authenticate-session`;

      return fetch(requestUrl, {
        headers: { 'Content-Type': 'application/json', sessionid: BPSystem.sessionId },
        method: 'POST',
        body: JSON.stringify({
          sessionId: BPSystem.sessionId,
        }),
      })
        .then(response => response.json())
        .then(response => response?.accessToken?.content)
        .catch(() => undefined);
    };

    document.getElementById('executeButton').addEventListener('click', async function() {
      const securityToken = await getHppSecurityToken();
      const script = document.createElement('script');
      script.src = "https://cdn.aws.billingplatform.com/hosted-payments-ui@release/lib.js";
      document.body.append(script);
      script.onload = function () {
        HostedPayments.renderPaymentForm({
          /** Required parameters: */
          targetSelector: 'body',
          amount: 100,
          environmentId: '096602aa-a033-4dad-815d-754105dbf6fc',
          billingProfileId: '1ba91f19-61f9-1c28-e063-ee043c0a3abe',
          paymentGateways: ['Adyen_CC', 'Adyen_DD'],
          apiUrl: "https://sandbox.billingplatform.com/noonlight_dev/hostedPayments/1.0/",
          securityToken: securityToken,
          /** Additional parameters: */
          walletMode: true,
          allowEditPrice: true,
          fullName: 'John',
          state: 'CO'
        });
      };
    });
  </script>
</body>
</html>
