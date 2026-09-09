# gaganjeet
obstacle avoiding robot
<!DOCTYPE html>

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

```
<title>Obstacle Avoidance Robot | Gagan Jeet Singh</title>

<style>
    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }

    body {
        font-family: Arial, Helvetica, sans-serif;
        background: #0f172a;
        color: #e2e8f0;
        line-height: 1.6;
    }

    header {
        background: #020617;
        padding: 25px 8%;
        border-bottom: 1px solid #334155;
        display: flex;
        justify-content: space-between;
        align-items: center;
    }

    .logo {
        font-size: 22px;
        font-weight: bold;
        color: #38bdf8;
    }

    nav a {
        color: #cbd5e1;
        text-decoration: none;
        margin-left: 25px;
        transition: 0.3s;
    }

    nav a:hover {
        color: #38bdf8;
    }

    .hero {
        text-align: center;
        padding: 80px 20px 60px;
        background: linear-gradient(135deg, #0f172a, #1e293b);
    }

    .hero h1 {
        font-size: 48px;
        margin-bottom: 15px;
        color: #f8fafc;
    }

    .hero p {
        font-size: 18px;
        color: #94a3b8;
        max-width: 700px;
        margin: auto;
    }

    .container {
        width: 90%;
        max-width: 1100px;
        margin: 50px auto;
    }

    .card {
        background: #1e293b;
        border: 1px solid #334155;
        border-radius: 15px;
        padding: 30px;
        margin-bottom: 30px;
        box-shadow: 0 10px 30px rgba(0, 0, 0, 0.25);
    }

    .card h2 {
        color: #38bdf8;
        margin-bottom: 15px;
        font-size: 28px;
    }

    .card p {
        color: #cbd5e1;
    }

    .steps {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        gap: 20px;
        margin-top: 25px;
    }

    .step {
        background: #0f172a;
        padding: 25px;
        border-radius: 12px;
        text-align: center;
        border: 1px solid #334155;
    }

    .step h3 {
        color: #38bdf8;
        margin-bottom: 10px;
    }

    .step p {
        font-size: 15px;
        color: #94a3b8;
    }

    .code-container {
        background: #020617;
        border-radius: 12px;
        overflow-x: auto;
        border: 1px solid #334155;
        margin-top: 20px;
    }

    .code-header {
        background: #111827;
        padding: 12px 18px;
        color: #94a3b8;
        font-family: monospace;
        border-bottom: 1px solid #334155;
    }

    pre {
        padding: 25px;
        margin: 0;
        color: #e2e8f0;
        font-family: Consolas, Monaco, monospace;
        font-size: 15px;
        line-height: 1.7;
        white-space: pre;
    }

    .highlight {
        color: #38bdf8;
        font-weight: bold;
    }

    .back-button {
        display: inline-block;
        margin-top: 20px;
        padding: 12px 22px;
        background: #38bdf8;
        color: #020617;
        text-decoration: none;
        border-radius: 8px;
        font-weight: bold;
        transition: 0.3s;
    }

    .back-button:hover {
        background: #7dd3fc;
        transform: translateY(-2px);
    }

    footer {
        text-align: center;
        padding: 30px;
        margin-top: 60px;
        border-top: 1px solid #334155;
        color: #64748b;
    }

    @media (max-width: 700px) {
        header {
            flex-direction: column;
            gap: 15px;
        }

        nav a {
            margin: 0 8px;
        }

        .hero h1 {
            font-size: 34px;
        }

        .steps {
            grid-template-columns: 1fr;
        }
    }
</style>
```

</head>

<body>

```
<!-- HEADER -->
<header>
    <div class="logo">Gagan Jeet Singh</div>

    <nav>
        <a href="#about">About</a>
        <a href="#logic">Logic</a>
        <a href="#code">Code</a>
    </nav>
</header>


<!-- HERO SECTION -->
<section class="hero">
    <h1>🤖 Obstacle Avoidance Robot</h1>

    <p>
        A Python-based obstacle avoidance system that continuously
        senses the environment, decides what to do, and controls
        the robot's motors.
    </p>
</section>


<main class="container">

    <!-- ABOUT -->
    <section class="card" id="about">
        <h2>About the Project</h2>

        <p>
            This project demonstrates a basic obstacle-avoidance
            system for a two-wheel differential-drive robot.
            A front distance sensor is used to detect obstacles.
            The robot moves forward when the path is clear and
            stops and turns when an obstacle is detected.
        </p>
    </section>


    <!-- LOGIC -->
    <section class="card" id="logic">
        <h2>How It Works</h2>

        <p>
            The robot repeatedly follows three basic steps:
        </p>

        <div class="steps">

            <div class="step">
                <h3>1. SENSE</h3>
                <p>
                    Read the current distance from the
                    distance sensor.
                </p>
            </div>

            <div class="step">
                <h3>2. DECIDE</h3>
                <p>
                    Compare the measured distance with
                    the safe distance.
                </p>
            </div>

            <div class="step">
                <h3>3. ACT</h3>
                <p>
                    Move forward if the path is clear.
                    Otherwise stop and turn.
                </p>
            </div>

        </div>
    </section>


    <!-- CODE -->
    <section class="card" id="code">

        <h2>Python Code</h2>

        <p>
            Complete Python code used for the obstacle
            avoidance logic:
        </p>

        <div class="code-container">

            <div class="code-header">
                Obstacle avoidance robot.py
            </div>

            <pre><code>SAFE_DISTANCE = 20  # cm
```

def get_distance():
# Read the distance from the sensor
return distance_sensor.read()

while True:
# 1. SENSE
distance = get_distance()

```
# 2. DECIDE
if distance > SAFE_DISTANCE:
    # 3. ACT - move forward
    left_motor.forward()
    right_motor.forward()

else:
    # Obstacle detected
    left_motor.stop()
    right_motor.stop()

    # Turn right
    left_motor.forward()
    right_motor.backward()

    sleep(0.5)</code></pre>

        </div>

    </section>


    <!-- PROJECT SUMMARY -->
    <section class="card">

        <h2>Project Summary</h2>

        <p>
            <span class="highlight">Safe Distance:</span>
            20 cm
        </p>

        <p>
            <span class="highlight">Movement:</span>
            Two-wheel differential drive
        </p>

        <p>
            <span class="highlight">Sensor:</span>
            Front distance sensor
        </p>

        <p>
            <span class="highlight">Control Logic:</span>
            Sense → Decide → Act
        </p>

        <a class="back-button" href="#">
            ↑ Back to Top
        </a>

    </section>

</main>


<!-- FOOTER -->
<footer>
    <p>
        © 2026 Gagan Jeet Singh • Obstacle Avoidance Robot
    </p>
</footer>
```

</body>
</html>
