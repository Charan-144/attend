<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <title>LeapStart | Employee Attendance</title>

  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>

  <link
    href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&display=swap"
    rel="stylesheet"
  >

  <style>

    :root {
      --teal: #0f4d68;
      --blue: #3bb3e3;
      --orange: #f5b95a;
      --text: #5b6470;
      --line: #e5eaf0;
      --white: #ffffff;
      --success: #15803d;
      --danger: #dc2626;
    }

    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      font-family: "Inter", system-ui, -apple-system, "Segoe UI", sans-serif;
      color: var(--text);

      background:
        linear-gradient(
          180deg,
          #e9f6fc 0,
          #ffffff 380px
        ) no-repeat #ffffff;
    }

    /* =========================
       NAVIGATION
    ========================== */

    nav {
      display: flex;
      align-items: center;
      justify-content: space-between;

      gap: 16px;

      padding: 14px 4vw;

      background: #ffffff;

      box-shadow:
        0 2px 14px rgba(15, 77, 104, 0.05);
    }

    .logo {
      display: flex;
      align-items: center;

      gap: 8px;

      text-decoration: none;
    }

    .logo .text {
      line-height: 1;
    }

    .logo b {
      display: block;

      font-size: 30px;

      font-weight: 800;

      color: var(--teal);

      letter-spacing: 0.01em;
    }

    .logo small {
      display: block;

      font-size: 9px;

      letter-spacing: 0.32em;

      color: var(--teal);

      margin-top: 3px;

      font-weight: 500;
    }

    .links {
      display: flex;

      gap: 28px;

      font-weight: 500;

      font-size: 16px;
    }

    .links a {
      color: var(--teal);

      text-decoration: none;
    }

    .links a:hover {
      color: var(--blue);
    }

    /* =========================
       BUTTON
    ========================== */

    .btn {
      font: inherit;

      font-weight: 600;

      border: 1px solid transparent;

      cursor: pointer;

      color: #ffffff;

      background: var(--teal);

      padding: 11px 24px;

      border-radius: 999px;

      text-decoration: none;

      font-size: 15px;

      box-shadow:
        0 8px 18px rgba(15, 77, 104, 0.18);

      transition: 0.2s ease;
    }

    .btn:hover {
      background: #0b4057;

      transform: translateY(-1px);
    }

    .btn:disabled {
      opacity: 0.65;

      cursor: wait;

      transform: none;
    }

    /* =========================
       HEADER
    ========================== */

    header {
      text-align: center;

      padding: 48px 18px 20px;
    }

    .badge {
      display: inline-flex;

      gap: 8px;

      align-items: center;

      border: 1.5px solid #8fd3ee;

      background: #dff3fb;

      color: #111111;

      border-radius: 999px;

      padding: 9px 20px;

      font-weight: 500;

      font-size: 15px;
    }

    h1 {
      margin: 26px 0 12px;

      color: var(--teal);

      font-weight: 700;

      font-size: clamp(34px, 7vw, 72px);

      line-height: 1.12;

      letter-spacing: -0.02em;
    }

    h1 .gradient {
      background:
        linear-gradient(
          90deg,
          var(--blue),
          #b9bf9c 50%,
          var(--orange)
        );

      -webkit-background-clip: text;

      background-clip: text;

      color: transparent;
    }

    .sub {
      font-size: clamp(16px, 2.2vw, 22px);

      line-height: 1.6;

      max-width: 760px;

      margin: 0 auto;
    }

    .sub em {
      font-style: normal;

      color: var(--orange);

      font-weight: 500;
    }

    /* =========================
       CLOCK
    ========================== */

    .clock {
      margin-top: 22px;

      color: var(--teal);
    }

    .clock strong {
      display: block;

      font-size: 34px;

      font-weight: 700;
    }

    /* =========================
       MAIN
    ========================== */

    main {
      max-width: 1040px;

      margin: 0 auto;

      padding: 10px 16px 50px;
    }

    .card {
      background: #ffffff;

      border: 1px solid var(--line);

      border-radius: 20px;

      padding: 22px;

      box-shadow:
        0 14px 40px rgba(15, 77, 104, 0.08);
    }

    .bar {
      display: flex;

      gap: 12px;

      flex-wrap: wrap;

      align-items: center;

      justify-content: space-between;

      margin-bottom: 14px;
    }

    /* =========================
       SEARCH
    ========================== */

    input {
      font: inherit;

      padding: 12px 18px;

      border: 1px solid var(--line);

      border-radius: 999px;

      width: 100%;

      max-width: 320px;

      color: var(--teal);

      outline: none;
    }

    input:focus {
      border-color: var(--blue);

      box-shadow:
        0 0 0 3px rgba(59, 179, 227, 0.12);
    }

    .hint {
      font-size: 13px;
    }

    /* =========================
       TABLE
    ========================== */

    .wrap {
      overflow-x: auto;
    }

    table {
      width: 100%;

      border-collapse: collapse;

      min-width: 760px;
    }

    th,
    td {
      text-align: left;

      padding: 14px 10px;

      border-bottom: 1px solid var(--line);

      font-size: 14px;

      vertical-align: middle;
    }

    th {
      font-size: 12px;

      text-transform: uppercase;

      letter-spacing: 0.06em;

      color: var(--teal);
    }

    td strong {
      color: var(--teal);
    }

    /* =========================
       ATTENDANCE STATUS
    ========================== */

    .ok {
      display: inline-block;

      background: #e6f7ee;

      color: var(--success);

      border-radius: 999px;

      padding: 6px 14px;

      font-weight: 600;

      font-size: 13px;
    }

    /* =========================
       LOCATION
    ========================== */

    .loc {
      font-size: 12.5px;

      max-width: 260px;

      word-break: break-word;
    }

    .loc a {
      color: var(--blue);

      text-decoration: none;
    }

    .loc a:hover {
      text-decoration: underline;
    }

    .err {
      color: var(--danger);

      font-size: 12.5px;
    }

    /* =========================
       TOAST
    ========================== */

    #toast {
      position: fixed;

      left: 50%;

      bottom: 24px;

      transform:
        translateX(-50%)
        translateY(30px);

      background: var(--teal);

      color: #ffffff;

      padding: 16px 22px;

      border-radius: 16px;

      box-shadow:
        0 14px 40px rgba(0, 0, 0, 0.25);

      opacity: 0;

      pointer-events: none;

      transition: 0.3s;

      max-width: 92vw;

      font-size: 14px;

      line-height: 1.5;

      z-index: 9999;
    }

    #toast.show {
      opacity: 1;

      transform:
        translateX(-50%)
        translateY(0);
    }

    #toast b {
      display: block;

      font-size: 17px;

      color: var(--orange);
    }

    /* =========================
       FOOTER
    ========================== */

    footer {
      text-align: center;

      font-size: 12px;

      padding: 18px;
    }

    /* =========================
       MOBILE
    ========================== */

    @media (max-width: 860px) {

      .links {
        display: none;
      }

      nav {
        padding: 12px 18px;
      }

      .logo b {
        font-size: 25px;
      }

      .logo small {
        font-size: 7px;
      }
    }

    @media (max-width: 600px) {

      header {
        padding-top: 32px;
      }

      h1 {
        font-size: 42px;
      }

      .card {
        padding: 15px;
      }

      .bar {
        align-items: stretch;
      }

      input {
        max-width: 100%;
      }

      .hint {
        text-align: center;
      }
    }

  </style>

</head>


<body>


  <!-- =========================
       NAVIGATION
  ========================== -->

  <nav>

    <a
      class="logo"
      href="https://leapstart.in"
      aria-label="LeapStart School of Technology"
    >

      <svg
        width="44"
        height="48"
        viewBox="0 0 44 48"
        aria-hidden="true"
      >

        <path
          d="M4 6l18-4 18 4v20c0 10-8 17-18 20C12 43 4 36 4 26z"
          fill="#fff"
          stroke="#0f4d68"
          stroke-width="3"
        />

        <path
          d="M14 30l12-16M26 14h-8M26 14v8"
          fill="none"
          stroke="#0f4d68"
          stroke-width="3.2"
          stroke-linecap="round"
          stroke-linejoin="round"
        />

        <path
          d="M10 12l8-2"
          stroke="#f5b95a"
          stroke-width="3"
          stroke-linecap="round"
        />

      </svg>


      <span class="text">

        <b>LEAPSTART</b>

        <small>
          SCHOOL OF TECHNOLOGY
        </small>

      </span>

    </a>


    <div class="links">

      <a href="https://leapstart.in/about">
        About
      </a>

      <a href="https://leapstart.in/programs">
        Programs
      </a>

      <a href="https://leapstart.in/school-of-skills">
        Skills
      </a>

      <a href="https://leapstart.in/admissions">
        Admissions
      </a>

      <a href="https://leapstart.in/faq">
        FAQ
      </a>

    </div>


    <a
      class="btn"
      href="https://leapstart.in/contact"
    >
      Contact us
    </a>

  </nav>


  <!-- =========================
       HEADER
  ========================== -->

  <header>

    <span class="badge">

      ✨ Employee Attendance ·

      <span id="badgeDate"></span>

    </span>


    <h1>

      Mark Your<br>

      <span class="gradient">
        Daily
      </span>

      Attendance

    </h1>


    <p class="sub">

      Find your name, tap
      <em>Check-in</em>
      and allow location access.

      Your
      <em>date, time and location</em>
      are recorded automatically.

    </p>


    <div class="clock">

      <strong id="time">
        --:--:--
      </strong>

      <span id="date"></span>

    </div>

  </header>


  <!-- =========================
       ATTENDANCE TABLE
  ========================== -->

  <main>

    <div class="card">

      <div class="bar">

        <input
          id="q"
          type="search"
          placeholder="Search your name…"
          autocomplete="off"
          aria-label="Search employee name"
        >

        <span class="hint">
          Location permission is required to check in.
        </span>

      </div>


      <div class="wrap">

        <table>

          <thead>

            <tr>

              <th>
                Employee
              </th>

              <th>
                Role
              </th>

              <th>
                Date
              </th>

              <th>
                Time
              </th>

              <th>
                Location
              </th>

              <th>
                Attendance
              </th>

            </tr>

          </thead>


          <tbody id="rows"></tbody>

        </table>

      </div>

    </div>

  </main>


  <!-- =========================
       FOOTER
  ========================== -->

  <footer>

    © 2026 LeapStart School of Technology.
    All rights reserved.

  </footer>


  <!-- TOAST MESSAGE -->

  <div id="toast"></div>


  <!-- =========================
       JAVASCRIPT
  ========================== -->

  <script>


    /* =====================================================
       GOOGLE APPS SCRIPT URL
       ===================================================== */

    var SCRIPT_URL =
      "https://script.google.com/macros/s/AKfycbyGA87BMSgqzQwsqaih70npcB4uCXA0cMqqtlan_fWxsvA51CUL5ZBKGVm0mPa0RdVp/exec";


    /* =====================================================
       EMPLOYEE LIST
       ===================================================== */

    var people = [

      ["Aarav Reddy", "Mentor"],

      ["Priya Sharma", "Operations"],

      ["Rohit Verma", "Software Engineer"],

      ["Ananya Iyer", "Data Scientist"],

      ["Karthik Naidu", "Tech Lead"],

      ["Sneha Kapoor", "HR Executive"],

      ["Vikram Singh", "Admissions"],

      ["Meera Nair", "QA Engineer"],

      ["Arjun Patel", "Designer"],

      ["Divya Menon", "Accounts"]

    ];


    /* =====================================================
       PAGE ELEMENTS
       ===================================================== */

    var tableBody =
      document.getElementById("rows");

    var searchBox =
      document.getElementById("q");

    var toast =
      document.getElementById("toast");


    /* =====================================================
       ESCAPE HTML
       ===================================================== */

    function esc(value) {

      return String(value).replace(
        /[&<>"']/g,

        function(character) {

          return {

            "&": "&amp;",
            "<": "&lt;",
            ">": "&gt;",
            '"': "&quot;",
            "'": "&#39;"

          }[character];

        }
      );

    }


    /* =====================================================
       TODAY
       ===================================================== */

    function today() {

      return new Date().toLocaleDateString(
        "en-CA",
        {
          timeZone: "Asia/Kolkata"
        }
      );

    }


    /* =====================================================
       LOCAL STORAGE
       ===================================================== */

    var STORAGE_KEY =
      "ls_att_" + today();

    var records = {};


    try {

      records =
        JSON.parse(
          localStorage.getItem(
            STORAGE_KEY
          ) || "{}"
        );

    } catch (error) {

      records = {};

    }


    function saveRecords() {

      try {

        localStorage.setItem(
          STORAGE_KEY,
          JSON.stringify(records)
        );

      } catch (error) {

        console.log(
          "Local storage unavailable."
        );

      }

    }


    /* =====================================================
       CLOCK
       ===================================================== */

    function updateClock() {

      var now =
        new Date();

      var timezoneOptions = {
        timeZone: "Asia/Kolkata"
      };


      document.getElementById(
        "time"
      ).textContent =

        now.toLocaleTimeString(
          "en-IN",

          Object.assign(
            {
              hour: "2-digit",
              minute: "2-digit",
              second: "2-digit",
              hour12: true
            },

            timezoneOptions
          )
        );


      document.getElementById(
        "date"
      ).textContent =

        now.toLocaleDateString(
          "en-IN",

          Object.assign(
            {
              weekday: "long",
              day: "numeric",
              month: "long",
              year: "numeric"
            },

            timezoneOptions
          )
        );


      document.getElementById(
        "badgeDate"
      ).textContent =

        now.toLocaleDateString(
          "en-IN",

          Object.assign(
            {
              day: "2-digit",
              month: "short",
              year: "numeric"
            },

            timezoneOptions
          )
        );

    }


    setInterval(
      updateClock,
      1000
    );

    updateClock();


    /* =====================================================
       LOCATION DISPLAY
       ===================================================== */

    function locationHTML(record) {

      var address =
        esc(record.address || "");


      var coordinates =

        Number(record.lat).toFixed(5)
        +
        ", "
        +
        Number(record.lng).toFixed(5);


      return (

        address

        +

        (
          record.address
            ? "<br>"
            : ""
        )

        +

        "<a " +
        "target='_blank' " +
        "rel='noopener noreferrer' " +

        "href='https://maps.google.com/?q=" +
        record.lat +
        "," +
        record.lng +
        "'>" +

        coordinates +

        "</a>"

      );

    }


    /* =====================================================
       RENDER EMPLOYEE TABLE
       ===================================================== */

    function render() {

      var search =
        searchBox.value
          .trim()
          .toLowerCase();


      tableBody.innerHTML = "";


      people.forEach(
        function(person, index) {

          var name =
            person[0];

          var role =
            person[1];


          if (
            search &&
            name
              .toLowerCase()
              .indexOf(search) < 0
          ) {

            return;

          }


          var record =
            records[name];


          var row =
            document.createElement("tr");


          var locationContent =
            record
              ? locationHTML(record)
              : "—";


          var attendanceContent =

            record

              ?

              "<span class='ok'>" +
              "✓ Logged in" +
              "</span>"

              :

              "<button " +
              "class='btn' " +
              "data-index='" +
              index +
              "'>" +
              "Check-in" +
              "</button>";


          row.innerHTML =

            "<td>" +
            "<strong>" +
            esc(name) +
            "</strong>" +
            "</td>" +

            "<td>" +
            esc(role) +
            "</td>" +

            "<td>" +
            (
              record
                ? esc(record.date)
                : "—"
            ) +
            "</td>" +

            "<td>" +
            (
              record
                ? esc(record.time)
                : "—"
            ) +
            "</td>" +

            "<td class='loc' id='location-" +
            index +
            "'>" +

            locationContent +

            "</td>" +

            "<td>" +

            attendanceContent +

            "</td>";


          tableBody.appendChild(row);

        }
      );

    }


    /* =====================================================
       TOAST MESSAGE
       ===================================================== */

    function showMessage(html) {

      toast.innerHTML =
        html;

      toast.className =
        "show";


      clearTimeout(
        showMessage.timer
      );


      showMessage.timer =

        setTimeout(
          function() {

            toast.className =
              "";

          },
          7000
        );

    }


    /* =====================================================
       GET ADDRESS FROM COORDINATES
       ===================================================== */

    function getAddress(
      latitude,
      longitude
    ) {

      var controller =
        new AbortController();


      var timeout =
        setTimeout(
          function() {

            controller.abort();

          },
          4000
        );


      var url =

        "https://nominatim.openstreetmap.org/reverse" +

        "?format=json" +

        "&zoom=18" +

        "&lat=" +
        encodeURIComponent(latitude) +

        "&lon=" +
        encodeURIComponent(longitude);


      return fetch(
        url,
        {
          signal:
            controller.signal
        }
      )

      .then(
        function(response) {

          if (!response.ok) {

            throw new Error(
              "Address service unavailable."
            );

          }

          return response.json();

        }
      )

      .then(
        function(data) {

          clearTimeout(
            timeout
          );

          return data.display_name || "";

        }
      )

      .catch(
        function() {

          clearTimeout(
            timeout
          );

          return "";

        }
      );

    }


    /* =====================================================
       CHECK-IN BUTTON
       ===================================================== */

    tableBody.addEventListener(
      "click",

      function(event) {

        var button =
          event.target.closest("button");


        if (!button) {
          return;
        }


        var index =
          Number(
            button.dataset.index
          );


        var employee =
          people[index];


        var name =
          employee[0];

        var role =
          employee[1];


        var locationCell =
          document.getElementById(
            "location-" + index
          );


        /* ---------------------------------------------
           CHECK GOOGLE APPS SCRIPT
        --------------------------------------------- */

        if (
          SCRIPT_URL.indexOf("http") !== 0
        ) {

          locationCell.innerHTML =

            "<span class='err'>" +

            "Attendance server not connected yet." +

            "</span>";

          return;

        }


        /* ---------------------------------------------
           CHECK LOCATION SUPPORT
        --------------------------------------------- */

        if (
          !navigator.geolocation
        ) {

          locationCell.innerHTML =

            "<span class='err'>" +

            "Location is not supported on this device." +

            "</span>";

          return;

        }


        /* ---------------------------------------------
           DISABLE BUTTON WHILE PROCESSING
        --------------------------------------------- */

        button.disabled =
          true;

        button.textContent =
          "Asking location…";

        locationCell.textContent =
          "Requesting location…";


        /* =================================================
           REQUEST LOCATION PERMISSION
        ================================================= */

        navigator.geolocation.getCurrentPosition(

          /* ===============================================
             LOCATION SUCCESS
          =============================================== */

          function(position) {

            button.textContent =
              "Getting address…";


            var coords =
              position.coords;


            var latitude =
              coords.latitude;

            var longitude =
              coords.longitude;

            var accuracy =
              Math.round(
                coords.accuracy
              );


            /*
              Get readable address first.
            */

            getAddress(
              latitude,
              longitude
            )

            .then(
              function(address) {

                button.textContent =
                  "Recording…";


                /*
                  -----------------------------------------
                  SEND ATTENDANCE TO GOOGLE APPS SCRIPT
                  -----------------------------------------
                */

                return fetch(
                  SCRIPT_URL,

                  {
                    method: "POST",

                    headers: {

                      "Content-Type":
                        "text/plain;charset=utf-8"

                    },

                    body:

                      JSON.stringify({

                        name:
                          name,

                        role:
                          role,

                        lat:
                          latitude,

                        lng:
                          longitude,

                        accuracy:
                          accuracy,

                        address:
                          address

                      })

                  }

                )

                .then(
                  function(response) {

                    if (!response.ok) {

                      throw new Error(
                        "Attendance server error."
                      );

                    }

                    return response.json();

                  }

                )

                .then(
                  function(result) {

                    if (!result.ok) {

                      throw new Error(
                        result.error ||
                        "Attendance recording failed."
                      );

                    }


                    /*
                      =====================================
                      CORRECTED RECORD STORAGE
                      =====================================

                      The address received above is
                      directly stored here.
                    */

                    records[name] = {

                      date:
                        result.date,

                      time:
                        result.time,

                      lat:
                        latitude,

                      lng:
                        longitude,

                      accuracy:
                        accuracy,

                      address:
                        address

                    };


                    /*
                      Save locally.
                    */

                    saveRecords();


                    /*
                      Refresh table.
                    */

                    render();


                    /*
                      Show success message.
                    */

                    showMessage(

                      "<b>✓ Logged in" +

                      (
                        result.duplicate
                          ? " (already recorded today)"
                          : ""
                      ) +

                      "</b>" +

                      esc(name) +

                      "<br>" +

                      esc(result.date) +

                      " · " +

                      esc(result.time) +

                      (
                        address
                          ? "<br>" +
                            esc(address)
                          : ""
                      )

                    );

                  }

                );

              }

            )

            .catch(
              function(error) {

                console.error(
                  error
                );


                button.disabled =
                  false;

                button.textContent =
                  "Check-in";


                locationCell.innerHTML =

                  "<span class='err'>" +

                  "Could not record attendance. " +

                  "Check your internet connection and try again." +

                  "</span>";

              }
            );

          },


          /* ===============================================
             LOCATION ERROR
          =============================================== */

          function(error) {

            button.disabled =
              false;

            button.textContent =
              "Check-in";


            if (
              error.code === 1
            ) {

              locationCell.innerHTML =

                "<span class='err'>" +

                "Location access denied. " +

                "Please allow location access in your browser settings and retry." +

                "</span>";

            }

            else if (
              error.code === 2
            ) {

              locationCell.innerHTML =

                "<span class='err'>" +

                "Your location could not be determined. Please try again." +

                "</span>";

            }

            else if (
              error.code === 3
            ) {

              locationCell.innerHTML =

                "<span class='err'>" +

                "Location request timed out. Please try again." +

                "</span>";

            }

            else {

              locationCell.innerHTML =

                "<span class='err'>" +

                "Could not get your location. Please try again." +

                "</span>";

            }

          },


          /* ===============================================
             LOCATION SETTINGS
          =============================================== */

          {
            enableHighAccuracy: true,

            timeout: 20000,

            maximumAge: 0
          }

        );

      }

    );


    /* =====================================================
       SEARCH
       ===================================================== */

    searchBox.addEventListener(
      "input",
      render
    );


    /* =====================================================
       INITIAL TABLE
       ===================================================== */

    render();

  </script>

</body>

</html>
