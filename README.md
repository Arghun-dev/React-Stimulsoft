# React-Stimulsoft

### initialze Stimulsoft in React

**First you have to notice that you should copy and paste the `.txt` file to your `public` folder. This is really `important`**

1. Create a folder called `stimulsoft` in public folder and copy the script tags and stylesheet links to it.

2. in head section of index.html: Add the stylesheet Link tag

```js
<head>
  <meta charset="utf-8" />
  <title>Hello React</title>
  <link rel="stylesheet" href="stimulsoft/stimulsoft.viewer.office2013.whiteblue.css">
</head>
```

3. in the body section: Add the script tags:

```js
<script crossorigin src="https://unpkg.com/react@16/umd/react.production.min.js"></script>
<script crossorigin src="https://unpkg.com/react-dom@16/umd/react-dom.production.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/babel-standalone/6.25.0/babel.min.js"></script>
<script src="stimulsoft/stimulsoft.reports.js"></script>
<script src="stimulsoft/stimulsoft.viewer.js"></script>
```

4. Then Create a react component for example App.js just like below:

```js
import React from 'react';
import './App.css';

class App extends React.Component {
  render() {
    return <div id="viewer"></div>;
  }

  componentDidMount() {
    console.log('Loading Viewer view');

    console.log('Creating the report viewer with default options');
    var viewer = new window.Stimulsoft.Viewer.StiViewer(null, 'StiViewer', false);

    console.log('Creating a new report instance');
    var report = new window.Stimulsoft.Report.StiReport();

    console.log('Load report from url');
    report.loadFile('Report.txt');

    console.log('Assigning report to the viewer, the report will be built automatically after rendering the viewer');
    viewer.report = report;

    console.log('Rendering the viewer to selected element');
    viewer.renderHtml('viewer');
  }
}

export default App;
```

**As you can see I have loaded File of stimulsoft as `.txt` file not `.mrt`**

That's it!!!
