# Supported Hazards

PetaBencana.id supports six types of disasters, as follow:

1. Flood
2. Earthquake
3. Extreme Wind
4. Forest Fire
5. Haze
6. Volcano

For the scope of this documentation, the disasters will have the following information

<table>
  <thead>
    <tr>
      <th style="text-align:left">Disaster Type</th>
      <th style="text-align:left">report_type</th>
      <th style="text-align:left">Attribute details</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Flood</td>
      <td style="text-align:left">flood</td>
      <td style="text-align:left">
        <p><b>flood_depth: </b>flood severity based on depth in cm
          <br />
        </p>
        <p>&lt; 70 cm : Minor</p>
        <p>70 - 150 cm : Moderate</p>
        <p>150 cm : Severe</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Earthquake</td>
      <td style="text-align:left">road</td>
      <td style="text-align:left"><b>accessabilityFailure: </b>the level of road damage affected by earthquake
        <br
        />
        <br />0 : &lt; 0,5 m (No Vehicle Access)
        <br />1 : 0,6 - 1 m (2-Wheel Vehicle Access)
        <br />2 or 3 : 1.1 - 1.8 m (4-Wheel Vehicle Access)
        <br />4 : &gt;1,9 m (Large Vehicle Access)</td>
    </tr>
    <tr>
      <td style="text-align:left">Earthquake</td>
      <td style="text-align:left">structure</td>
      <td style="text-align:left">
        <p><b>accessabilityFailure: </b>the level of structure damage affected by
          earthquake</p>
        <p></p>
        <p>0 : Cracking
          <br />1 : Partially Collapse
          <br />2 : Fully Collapse</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Extreme Wind</td>
      <td style="text-align:left">wind</td>
      <td style="text-align:left">
        <p><b>impact</b>: level of disruption caused by extreme wind</p>
        <p>0 : Low Disruption
          <br />1 : Medium Disruption
          <br />2 : High Disruption</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Haze</td>
      <td style="text-align:left">haze</td>
      <td style="text-align:left">
        <p><b>visibility</b>: the distance one can see as determined by light and
          weather conditions</p>
        <p>0: can see but need to wear a mask</p>
        <p>1: can see but not clean enough to drive</p>
        <p>2: can barely see, too dangerous to go out</p>
        <p></p>
        <p><b>airQuality</b>: described by symptoms felt by humans</p>
        <p>0 or 1: Poor Air Quality
          <br />2: Severe Air Quality
          <br />3 or 4 : Hazardous Air Quality</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Forest Fire</td>
      <td style="text-align:left">fire</td>
      <td style="text-align:left"><b>fireRadius</b>: the radius of a forest fire estimated by the human
        eye</td>
    </tr>
  </tbody>
</table>

