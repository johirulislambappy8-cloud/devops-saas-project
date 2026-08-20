const { spawn } = require("child_process");
const http = require("http");

const app = spawn("node", ["app.js"]);

setTimeout(() => {
  http.get("http://localhost:3000", (res) => {
    if (res.statusCode === 200) {
      console.log("Automated test passed");
      app.kill();
      process.exit(0);
    } else {
      console.error("Automated test failed");
      app.kill();
      process.exit(1);
    }
  }).on("error", (err) => {
    console.error("Automated test failed:", err.message);
    app.kill();
    process.exit(1);
  });
}, 2000);
