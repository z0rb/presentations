@title[Title Page]

# Arrowhead
#### Middleware for the CPS/IoT Ecosystem

---

@title[Arrowhead]

#### Arrowead in Comparison

<ul>
  <li class="fragment">Cloud vs. Inter-Device Approach</li>
  <li class="fragment">Global vs. Local Cloud</li>
  <li class="fragment">Proprietary vs. Open/Free</li>
</ul>

---

@title[Core Services]

#### Core Systems

Mandatory (minimal) local cloud systems:

<ul>
  <li class="fragment">Service Registry</li>
  <li class="fragment">Orchestrator</li>
  <li class="fragment">Authorization and Authentication (and Accounting)</li>
</ul>

---
@title[Automation Support Systems]

#### Automation Support Systems

+++
@title[M3 Implemented Systems]

| System |Implemented in M3|
|--------|-------------------|
| Plant Description | No |
| Configuration | No |
| System Registry | No |
| Device Registry | No |
| Event Handler | No |
| QoS Manager | Yes |
| Historian | No |
| Gatekeeper | Yes |
| Translation | No |
| Gateway | Yes |

---

@title[Provider Registrator]

#### Provider Registrator

<ul>
  <li>Enables constrained devices registration within a local cloud.</li>
  <li>Standalone or Extended</li>
  <li>Basis for self-registering services.</li>
</ul>
+++
@title[Extended Provider Registrator]

#### Extended Provider Registrator

The registration functionality can be imported into a Java project using a WAR overlay.

```xml
<dependencies>
  ...
  <dependency>
    <groupId>at.ac.tuwien.cpsg.arrowhead.providers</groupId>
    <artifactId>provider-registrator</artifactId>
    <version>0.0.1-SNAPSHOT</version>
    <type>war</type>
    <scope>runtime</scope>
  </dependency>
  ...
<dependencies>
```

---

@title[Generalized Consumer]

#### Generalized (UI) Consumer

- Consumes a configured service
- Handles intra-cloud authorization
- Handles inter-cloud authorization
- Polls the configured consumed service in predefined intervals
- Displays the query information and currently returned payload in a very simple UI

---

@title[Dockerization]

#### Dockerized Demo System (Cloud of Clouds)

Two clouds have been dockerized using docker compose.

+++
@title[Producer Cloud]

#### Producer Cloud

- Cloud runs core Arrowhead framework systems as containers
- Also runs database, gateway and gatekeeper systems as containers
- Runs an extended provider registrator providing temperature, humidity and illumination readings
- Tested on RaspberryPi 3B

+++
@title[Consumer Cloud]

#### Consumer Cloud

- Cloud runs core Arrowhead framework systems as containers
- Also runs database, gateway and gatekeeper systems as containers
- Runs the UI-Consumer consuming the producer cloud provided services
- Tested on development machine

---

@title[State of the Community]

#### State of the Community

- Currently academia with partners
- Closed but appreceated communication
- Plans for a broader open community are unclear
- Zero-transparency project management

---

@title[State of the Code]

#### State of the Code

- Ad-Hoc development
- Missing Unit/Integration/Regression Tests
- Unclear if build system exists
- No maven repository usage
- Quality assurance needs to be overhauled/introduced and automated
