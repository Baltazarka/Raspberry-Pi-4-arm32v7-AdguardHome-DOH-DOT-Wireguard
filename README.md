<h3 align="center">Raspberry-Pi-4-arm32v7-AdguardHome-DOH-DHT-Wireguard</h3>

<p align="center">
  <ul>
  <li>After configuring the docker-compose.yml and .env files, you have to start the containers with: <code>docker-compose up -d</code></li>
  <li>Then, you can access the AdGuardHome web interface at: <code>http://&lt;Server_IP&gt;:8081/</code></li>
    <li>Then, you can access the Wireguard web interface at: <code>http://&lt;Server_IP&gt;:8082/</code></li>
  <li><code>IMPORTANT</code>: In Listen Interfaces option choose <code>eth0</code> (or another name, it depends on your system) and select next</li>
  <li>Set up <code>username</code> &amp; <code>password</code> and then login <code>http://&lt;Server_IP&gt;:80/</code></li>
  <li><code>IMPORTANT</code>: In general settings, set "Query logs retention" to 24 hours. (I read that for some people logs fill up which slows down Pi and needing a reboot)</li>
  <li>In AdGuard homepage under settings, select "DNS settings"
  <ul>
  <li>Delete everything from both <em><strong>Upstream</strong></em> and <em><strong>Bootstrap DNS</strong></em> server options and add the following for:</li>
  <li>DNS over TLS (Unbound) : <code>10.8.1.10:53</code></li>
  <li>DNS over HTTPS/Oblivious DNS over HTTPS : <code>10.8.1.20:5053</code> (Cloudflared tunnel)</li>
  <li>TLS forwarder (Stubby) : <code>10.8.1.30:5353</code></li>
  </ul>
  </li>
  <li><code>IMPORTANT:</code> Check "<a href="https://adguard.com/en/blog/in-depth-review-adguard-home.html#dns"><b>Parallel Request</b></a>" option for DNS resolvers to work simultaneously.</li>
  <li>Then in DNS setting look for DNS cache configuration section and set cache size to 0 (caching is already handled by Unbound) and click apply.</li>
  <li>Click apply and test upstreams</li>
</ul>
</p>

<p align="center">
  <table>
    <tr>
      <td width="50%;">
          <img style="display: block;" align="center" src="https://user-images.githubusercontent.com/50296997/175570800-38980dd5-7ef9-4755-9a9f-a2f146ec69f5.png">
          <img style="display: block;" align="center" src="https://user-images.githubusercontent.com/50296997/175570912-0f8ecbc6-2b73-41f9-b1db-13cf29c1df81.png">
      </td>
      <td width="50%;">
          <code style="margin: auto 0;" align="center"><a href="https://1.1.1.1/help">https://1.1.1.1/help</a></code>
          <img style="display: block;" align="center" src="https://user-images.githubusercontent.com/50296997/175571556-ad189bd3-cf44-439a-8ca9-08132bc296fc.png">
      </td>
    </tr>
  </table>
  <table>
    <tr>
      <td width="100%;">
          <img align="center" src="https://user-images.githubusercontent.com/50296997/175570157-668c29b5-c5b2-4cc5-817f-2e1988002f4b.png">
          <img align="center" src="https://user-images.githubusercontent.com/50296997/175570237-a0ef34e6-5da1-46e5-9f0d-2b0b59107f3d.png">
          <img align="center" src="https://user-images.githubusercontent.com/50296997/175570289-6f9ada4d-2a93-4b20-bcdd-c387fd7a1367.png">
          <img align="center" src="https://user-images.githubusercontent.com/50296997/175573061-8d4641e1-f920-45e5-91a5-e57dec1b6885.png">
      </td>
    </tr>
  </table>
</p>
