# React Testing and Deployment

## Testing

- Snapshots - make assertions on EXACT rendered markup
- Render Testing - use jquery inspection to test virtual DOM
- shallow testing - execute and render container components, not children
- mounting - execute all and children, allows for checking of state

## deployment

- node server is NOT what is deployed, it just helps you render
- `npm run build` builds the sight with just the basic files

### github pages deploy

- incorporate secret toke in the repo and employ `actions` for testing

### deploy to AWS

- create a bucket
  - storage containers (folders)
- Objects
  - files in the buckets
  - upload to a bucket
- set up to serve websites
  - `static web hosting` on properties tab

### aws amplify deploy

- create Amplify workflow
- point workflow at git repo
- merge to master (auto builds now)

### deploy to netlify

- create new app
- point at github repot
- merge to master (auto builds)

### deploy to old-school host

- FTP to hosting company with a tool (transmit, filezilla, etc.)
- navigate to web root
- upload contents to `build` folder

### addtionional resources

#### articles

[jest testing with react](https://create-react-app.dev/docs/running-tests/)
[snapshot testing](https://jestjs.io/docs/en/snapshot-testing)
[static rendering - enzyme](https://airbnb.io/enzyme/docs/api/shallow.html)
[shallow mounting - enzyme](https://airbnb.io/enzyme/docs/api/render.html)
[full mounting - enzyme](https://airbnb.io/enzyme/docs/api/mount.html)

#### bookmark

[selenium](https://www.seleniumhq.org/)
[web driver](http://webdriver.io/)
[nightmare](http://www.nightmarejs.org/)
[enzyme](https://airbnb.io/enzyme/docs/api/)
[AWS](http://aws.amazon.com/)
[Netlify](http://www.netlify.com/)