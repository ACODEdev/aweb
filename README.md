---
id: the-basics
title: The Basics
sidebar_label: The Basics
slug: /
---

## Put a locally running HTTP, HTTPS or TLS app on the internet

localhost.run is a client-less tool to instantly make a locally running application available on an internet accessible URL.

All major operating systems already have SSH installed, and localhost.run uses SSH as a client, so no download is necessary to use the service and no account setup is needed for free domains.

To connect an internet domain to an application running locally on port 8080 open a command terminal and run:

```bash
ssh u0_a348@192.168.2.104 -p 8022
```

import { useState } from 'react'

export const PortChooser = () => {
  const [port, setPort] = useState(3000);
    const [rport, setRPort] = useState(3000);
  return (
    <>
      Enter The;
      <label for="port"> Name Of Your Site:</label>
      &nbsp;
      <input style={{width: "100%"}} type="text" id="port" name="port" min="1" max="65535" maxlength="10" value={port} onChange={(event) => setPort(event.target.value)} />
      ?
      use this command:
      <pre><code parentName="pre" {...{
              "className": "bash"
            }}>{`mkdir ${port} 
            cd ${port}
            python3 -m http.server ${rport}
            ssh -R 80:localhost:${rport} localhost.run
`}</code></pre>
    </>
  )
};

<PortChooser />
