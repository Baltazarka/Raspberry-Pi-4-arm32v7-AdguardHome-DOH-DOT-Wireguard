<h3 align="center">Raspberry-Pi-4-arm32v7-AdguardHome-DOH-DOT-Wireguard</h3>

<p align="center">
    <ul>
        <li>A docker-compose.yml és .env fájlok konfigurálása után a tárolókat a következővel kell elindítani:
            <code>docker-compose up -d</code></li>
        <li>Ezután elérheted az AdGuardHome webes felületét a következő címen:
            <code>http://&lt;Server_IP&gt;:8081/</code></li>
        <li>Ezután elérheted a Wireguard webes felületét a következő címen: <code>http://&lt;Server_IP&gt;:8082/</code>
        </li>
        <li><code>FONTOS</code>: A Listen Interfaces opcióban válasszd az <code>eth0</code> lehetőséget (vagy egy másik
            nevet, ez a rendszertől függ), majd válasszd a következőt</li>
        <li>A <code>felhasználónév</code> &amp; <code>jelszó</code>, majd jelentkezzen be
            <code>http://&lt;Server_IP&gt;:80/</code></li>
        <li><code>FONTOS</code>: Általános beállításokban állítsd a „Lekérdezési naplók megtartása” lehetőséget 24 órára.
        </li>
        <li>Az AdGuard kezdőlapján a beállítások alatt válassza a „DNS-beállítások” lehetőséget.
            <ul>
                <li>Töröljön mindent az <em><strong>Upstream DNS-kiszolgálók</strong></em> és a <em><strong>Bootstrap DNS kiszolgálók</strong></em>
                    szerverbeállításokból, és add hozzá a következőket:</li>
                <li>DNS over TLS (Unbound) : <code>10.8.1.10:53</code></li>
                <li>DNS over HTTPS/Oblivious DNS over HTTPS : <code>10.8.1.20:5053</code> (Cloudflared
                    tunnel)</li>
                <li>TLS forwarder (Stubby): <code>10.8.1.30:5353</code></li>
            </ul>
        </li>
        <li><code>FONTOS:</code> Ellenőrizd a 
            „<a href="https://adguard.com/en/blog/in-depth-review-adguard-home.html#dns"><b>Párhuzamos lekérések</b></a>"
            opciót, hogy a DNS-feloldók egyidejűleg működjenek.</li>
        <li>Ezután a DNS-beállításokban keresd meg a DNS gyorsítótár beállításai részt, és állítsa a gyorsítótár
            méretét 0-ra (a gyorsítótárazást már kezeli az Unbound), majd kattints az Mentés gombra.</li>
        <li>Kattints az Upstreamek tesztelésére majd az Alkalmaz gombra</li>
    </ul>
</p>

<p align="center">
    <table>
        <tr>
            <td width="50%;">
                <img style="display: block;" align="center"
                    src="https://user-images.githubusercontent.com/50296997/175570800-38980dd5-7ef9-4755-9a9f-a2f146ec69f5.png">
                <img style="display: block;" align="center"
                    src="https://user-images.githubusercontent.com/50296997/175570912-0f8ecbc6-2b73-41f9-b1db-13cf29c1df81.png">
            </td>
            <td width="50%;">
                <code style="margin: auto 0;" align="center"><a
                        href="https://1.1.1.1/help">https://1.1.1.1/help</a></code>
                <img style="display: block;" align="center"
                    src="https://user-images.githubusercontent.com/50296997/175571556-ad189bd3-cf44-439a-8ca9-08132bc296fc.png">
            </td>
        </tr>
    </table>
    <table>
        <tr>
            <td width="100%;">
                <img align="center"
                    src="https://user-images.githubusercontent.com/50296997/175570157-668c29b5-c5b2-4cc5-817f-2e1988002f4b.png">
                <img align="center"
                    src="https://user-images.githubusercontent.com/50296997/175570237-a0ef34e6-5da1-46e5-9f0d-2b0b59107f3d.png">
                <img align="center"
                    src="https://user-images.githubusercontent.com/50296997/175570289-6f9ada4d-2a93-4b20-bcdd-c387fd7a1367.png">
                <img align="center"
                    src="https://user-images.githubusercontent.com/50296997/175573061-8d4641e1-f920-45e5-91a5-e57dec1b6885.png">
            </td>
        </tr>
    </table>
</p>
