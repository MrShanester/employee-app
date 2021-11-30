<template>
  <div id="app" class="small-container">
    <h1>Employees</h1>

    <employee-form @add:employee="addEmployee" />
    <employees-table :employees="employees" />
    <div class="style">
      <button v-on:click="business()">Initiate Business</button>
      <button v-on:click="animate()">Initiate SQUARE</button>
    </div>
    <svg
      version="1.1"
      id="handshake"
      xmlns="http://www.w3.org/2000/svg"
      xmlns:xlink="http://www.w3.org/1999/xlink"
      x="0px"
      y="0px"
      xml:space="preserve"
    >
      <g>
        <path
          class="st0"
          d="M42,260v212h114v-25h48.5L399,602h17l18-8.5l6-22.5l32,6l17-9l11.7-24l18.3,7h25c0,0,1-5,6-10s9-20,9-20
		s22,4,26,4s20.6-5,20.6-5s8.4-15,8.4-19s-8.4-19-8.4-19l-9.6-12l33-29.2h63V473h110V260H688v35h-66l-77-41.1l-67-9.9l-56,26.1
		L385.7,282l-77.7-2h-47l-39,21h-63v-41H42z"
        />
        <path
          class="st1"
          d="M314,349.8c19.2-20.8,38.2-42.2,58.9-61.6h-99.1L230,309.3c-0.3,0.2-4.4,1-4.4,1h-59.9v127.2h31.8
		c2.7,0,5.2,1.1,7,2.8c10.2,8.4,167,137.4,195.2,150.9c19.1,9.2,39.1-11.4,27.9-20.4c-19-15.6-38.2-31.2-57.4-46.8l12.8-15.7
		c4.7,3.8,73.6,55.9,73.6,55.9c28.9,13.7,40.3-10.8,20.8-26.8l-77.1-62.8l12.8-15.7c26.1,21.2,73,65.7,104.2,81.1
		c26.6,12.6,41.2-8.1,20.5-26.9l-77.1-62.9l12.8-15.7c25.7,21,73.8,66,101.8,79.5c28.8,13.8,40.2-11,20.7-26.8l-10.5-8.6
		c-9.6,0.4-19.6-2.9-29-12.8L437.8,341.6c-14.5,14.4-47.7,46.1-70.2,60.4C329,426.5,273.9,393,314,349.8L314,349.8z M165.7,290h57.7
		l43.1-20.7c1.5-0.9,3.2-1.4,5-1.4h125c43.5-33.6,93.2-49.9,158.1-16.6l65,33.3h61.4v-34.9c43.7,0,87.5,0,131.2,0v233.4
		c-43.8,0-87.5,0-131.2,0V452h-49.8c-4.3,4.8-12.6,13-22.9,19.1l0.5,0.4c37.4,30.4,9,84.4-41.2,61.2c-2,32.6-36.2,36.9-60.4,24.8
		c-2,28.2-31.4,37.1-56.7,26.2c-5.9,25.5-36.7,36.6-59.4,25.8c-28.8-13.8-174.7-133.2-197.1-151.6h-28.2v25.4
		c-43.8,0-87.5,0-131.2,0V249.8c43.7,0,87.5,0,131.2,0L165.7,290L165.7,290z M145.4,270.1H54.8v192.8h90.7V270.1z M680.9,305
		l-63.7,0c-1.5,0-3.1-0.4-4.6-1.1l-67.2-34.5c-98.7-50.7-158.3,34.3-216.5,94.2c-24.7,26.6,12,31.4,27.8,21.4
		c29.2-18.5,49.2-43.6,74.3-65.1c4-3.8,10.5-3.7,14.3,0.4L571,451.8c17.6,18.4,43.2-10.9,47.1-15.6c1.8-2.7,4.9-4.5,8.4-4.5h54.4
		V305z M791.9,270.1h-90.7v192.8h90.7V270.1z"
        />
      </g>
    </svg>
  </div>
</template>

<style>
button {
  background: #009435;
  border: 1px solid #009435;
}

.small-container {
  max-width: 680px;
}

.style {
  text-align: center;
  font-style: italic !important;
}
</style>

<script>
import EmployeesTable from "./components/EmployeesTable.vue";
import EmployeeForm from "./components/EmployeeForm.vue";
import Two from "two.js";
import THREE from "three.js";

export default {
  name: "app",
  components: {
    EmployeesTable,
    EmployeeForm,
  },
  data() {
    return {
      employees: [
        {
          id: 1,
          name: "Richard Hendricks",
          email: "richard@piedpiper.com",
        },
        {
          id: 2,
          name: "Bertram Gilfoyle",
          email: "gilfoyle@piedpiper.com",
        },
        {
          id: 3,
          name: "Dinesh Chugtai",
          email: "dinesh@piedpiper.com",
        },
      ],
    };
  },
  methods: {
    addEmployee(employee) {
      const lastId = this.employees.length > 0 ? this.employees[this.employees.length - 1].id : 0;
      const id = lastId + 1;
      const newEmployee = { ...employee, id };

      this.employees = [...this.employees, newEmployee];
    },
    business: function () {
      var hands, arms;
      var two = new Two({
        fullscreen: true,
        autostart: true,
      }).appendTo(document.body);

      var elem = document.querySelector("#handshake");
      var svg = two.interpret(elem);

      elem.style.display = "none";

      hands = svg;
      hands.children[0].center();
      hands.children[0].position.y = 10;
      hands.children[0].children[0].fill = "white";
      hands.children[0].children[1].fill = "blue";
      hands.children[0].scale = 0.25;

      var points = [];
      var width = two.width * 1.5;
      for (var i = 0; i < 32; i++) {
        var pct = i / 31;
        var x = pct * width - width / 2;
        var y = 0;
        points.push(new Two.Anchor(x, y));
      }

      arms = two.makePath(points, false, true);
      arms.linewidth = 30;
      arms.noFill();
      arms.stroke = "blue";

      two.scene.position.set(two.width / 2, two.height / 2);
      two.scene.scale = 1.33;
      two.add(hands);

      two.bind("update", function (frameCount, timeDelta) {
        if (!timeDelta) {
          return;
        }

        var t = frameCount / 50;
        var theta;
        var amplitude = 133;

        for (var i = 0; i < arms.vertices.length; i++) {
          var pct = i / (arms.vertices.length - 1);
          var v = arms.vertices[i];
          theta = Math.PI * (t + pct);
          v.y = amplitude * Math.sin(theta);
        }

        theta = Math.PI * (t + 0.5);
        hands.position.y = amplitude * Math.sin(theta);

        var a = arms.getPointAt(0.49);
        var b = arms.getPointAt(0.51);

        theta = Math.atan2(b.y - a.y, b.x - a.x);
        hands.rotation = theta;
      });
    },
    animate: function () {
      const scene = new THREE.Scene();
      const camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000);

      const renderer = new THREE.WebGLRenderer();
      renderer.setSize(window.innerWidth, window.innerHeight);
      document.body.appendChild(renderer.domElement);

      const geometry = new THREE.BoxGeometry();
      const material = new THREE.MeshBasicMaterial({ color: 0x00ff00 });
      const cube = new THREE.Mesh(geometry, material);
      scene.add(cube);

      camera.position.z = 5;

      const animate = function () {
        requestAnimationFrame(animate);

        cube.rotation.x += 0.01;
        cube.rotation.y += 0.01;

        renderer.render(scene, camera);
      };

      animate();
    },
  },
};
</script>
