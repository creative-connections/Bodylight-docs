# Tutorial to use Bodylight.js 2.0

This tutorial will guide you from model source code to functional interactive web simulator. 

The basic simulator will guide you from the following Model

```Modelica
model SecondOrderSystemInitParams
  "A second order rotational system with initialization parameters"
  type Angle=Real(unit="rad");
  type AngularVelocity=Real(unit="rad/s");
  type Inertia=Real(unit="kg.m2");
  type Stiffness=Real(unit="N.m/rad");
  type Damping=Real(unit="N.m.s/rad");
  parameter Angle phi1_init = 0;
  parameter Angle phi2_init = 1;
  parameter AngularVelocity omega1_init = 0;
  parameter AngularVelocity omega2_init = 0;
  parameter Inertia J1=0.4 "Moment of inertia for inertia 1";
  parameter Inertia J2=1.0 "Moment of inertia for inertia 2";
  parameter Stiffness c1=11 "Spring constant for spring 1";
  parameter Stiffness c2=5 "Spring constant for spring 2";
  parameter Damping d1=0.2 "Damping for damper 1";
  parameter Damping d2=1.0 "Damping for damper 2";
  Angle phi1 "Angle for inertia 1";
  Angle phi2 "Angle for inertia 2";
  AngularVelocity omega1 "Velocity of inertia 1";
  AngularVelocity omega2 "Velocity of inertia 2";
initial equation
  phi1 = phi1_init;
  phi2 = phi2_init;
  omega1 = omega1_init;
  omega2 = omega2_init;
equation
  omega1 = der(phi1);
  omega2 = der(phi2);
  J1*der(omega1) = c1*(phi2-phi1)+d1*der(phi2-phi1);
  J2*der(omega2) = c1*(phi1-phi2)+d1*der(phi1-phi2)-c2*phi2-d2*der(phi2);
end SecondOrderSystemInitParams;
```

into interactive web simulator:

## Brief steps 

1. web simulator is a general web page in HTML
2. web simulator can be written in Markdown - the 'markdown-it' renderer is used to render HTML output
3. the Bodylight.js components are distributed as reusable web components - custom elements, which can be written next to HTML or Markdown - the 'bodylight.js' renderer is used to render HTML/JS output
4. The further tutorial will guide you to produce Markdown documents enriched with bodylight web components - however any other markup based on HTML supporting HTML and leaving HTML tags (and custom elements) on browser interpretation can be used.

## Basic web simulator

To produce single interactive web simulators you need only to use Bodylight.js-FMU-Compiler and Bodylight.js-Components.
Basic guide will follow you to:

1. Compile Modelica model to FMU with source codes including solver.
2. Compile FMU to Javascript with embedded WebAssembly, this allows to run model using FMI api inside browser.
3. Create web simulator document.

<a href='#basic1exportdymola' class="w3-button w3-theme-l1">Basic Web Simulator Tutorial - start from Dymola</a>

<a href='#basic2exportom' class="w3-button w3-theme-l1">Basic Web Simulator Tutorial - start from OpenModelica</a>

## Advanced web simulator

To produce multipage interactive web simulators you will need Bodylight.js-FMU-Compiler Bodylight.js-Components and Bodylight-Editor or Bodylight-Composer tool. 

Advanced guide will follow you to:
1. Compile Modelica model to FMU with source codes including solver.
2. Compile FMU to Javascript with embedded WebAssembly (this allows to run model FMU inside browser.
3. Create web simulator project in Bodylight Editor.

<a href='#advanced1exportdymola' class="w3-button w3-theme-l1">Advanced Web Simulator Tutorial - start from Dymola</a>

<a href='#advanced2exportom' class="w3-button w3-theme-l1">Basic Web Simulator Tutorial - start from OpenModelica</a>

 