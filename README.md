You can use Homebrew or the precompiled binary to install watch if you don't already have it:

<b>Homebrew</b>:<br />
<code>brew install watch</code>

<b>Open terminal, then execute</b>:<br />
<code>curl -O http://ktwit.net/code/watch-0.2-macosx/watch</code><br />
<code>chmod +x watch</code><br />
<code>./watch</code><br />
<code>sudo mv watch /usr/local/bin/</code>

<b>Create a new file</b>:<br />
<code>touch miner.sh</code><br />
<code>chmod +x miner.sh</code>

<b>Use an editor to edit file</b>:<br />
<code>vi miner.sh</code><br />

<h2>Miner - General Info </h2>
#!/bin/bash

curl -k --silent https://api.nanopool.org/v1/eth/user/:your_wallet_address |

jq -r '{balance:.data.balance, curent_hashrate:.data.hashrate, six_hr_avg:.data.avgHashrate.h6}, {workers:.data.workers[0].id, hashrate:.data.workers[0].hashrate}, {workers:.data.workers[1].id, hashrate:.data.workers[1].hashrate}' |

sed 's/[{}]//g' |
tr -d '""' |
tr -d ','
<br /><br />
<b>Save file and run</b>:</br>
<code>watch -n 10 --no-title /.miner.sh</code>

<b>Output</b>:<br />
balance: 0.11324834<br />
total_hashrate: 1025.0<br />
six_hr_avg: 1030.5<br /><br />

workers: GTX1070<br />
hashrate: 1030.5<br /><br />


workers: GTX1070x2<br />
hashrate: 1030.5
