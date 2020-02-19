# Odoo antivirus
<p>Openerp 10.0 antivirus plugin.</p>

<h4>Clamav daemon and virustotal quickstart:</h4>
<ul>
<li>To install clamav deamon: [ubuntu/debian]: > <b>sudo apt-get install clamav clamav-daemon</b></li>
<li>To update virus definitions: > <b>sudo freshclam</b></li>
<li>To check if it's running: > <b>ps ax | grep [c]lamd</b></li>
<li>To edit options like max filesize etc. > <b>sudo nano /etc/clamav/clamd.conf then sudo /etc/init.d/clamav-daemon restart</b></li>
<li>For other distributions check clamav manual</li>
<li>For use of virustotal api: <b>pip install virustotal-api</b></li>
<li>Virustotal api needs api key, it can be obtained after registering www.virustotal.com</li>
</ul>

<h4>Configuration quickstart:</h4>
<ul>
<li>Add new configuration in Antivirus->Config menu</li>
<li>Fill all fields, for virustotal api keys You should register at virustotal.com, it's free.</li>
<li>Check "Use this config". Only one config can be active at once.</li>
<li>Add new scanner named antivir.scanner.clamav .</li>
</ul>

<h4>Extending hints:</h4>
<ul>
<li>Adding new scanners is easy You should create file like <a href="https://github.com/nuncjo/Odoo-antivirus/blob/master/antivir/scanners/scanner_clamav.py">scanner_clamav.py</a>
</li>
<li>There is nice Python Wrapper library working with many commercial AV's https://github.com/nuncjo/multiav </li>
</ul>


<h4>Features:</h4>
<ul>
    <li>Scans files on attachments create</li>
    <li>Full list of ClamAV features at http://www.clamav.net/</li>
    <li>Online scan by Virustotal api: manual hash checking for quarantined files analysis, could be simply extended if needed.</li>
</ul>

<h4>Policy:</h4>
<ul>
    <li>Default infected files policy: delete in frontend, store in quarantine for further analysis, blacklisting etc.</li>
    <li>Unsafe files scanned by cron are hidden from user. This can be customized by using ir.rule in security.xml.</li>
    <li>Files hidden after scan can be restored from quarantine by admin by checking "Virus safe" or/and moving to whitelist.</li>
</ul>

<h4>Notice:</h4>
<ul>
    <li>Clamav offers only basic protection compared to commercial antivirus software, I encourage You to extend this plugin to use more sophisticated protection.</li>
    <li>Odoo antivirus is rather skeleton for extending with dedicated commercial antivirus solutions.</li>
</ul>

<h4>Future extension possibilites:</h4>
<ul>
    <li>Scanning website urls in mails in external services/checking in phising databases etc.</li>
    <li>More pre defined scanners.</li>
    <li>Predefined hash databases (like http://virusshare.com/).</li>
    <li>Hash checking for every file in archives</li>
    <li>Antispam mail extension.</li>
    <li>Periodic reports and statistics.</li>
</ul>

Source code: https://github.com/nuncjo/Odoo-antivirus
