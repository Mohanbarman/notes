# Web Performance

## Web vitals

### FCP (First contentful paint)
Displays how long it takes for a website to render the first visual on screen

### LCP (Largest contentful paint)
Web pages load the content over time when opened, first contentful paint is anything visual that is rendered first like image, video and text the *Largest Contentful Paint* is when all the contents are rendered on the page. To achieve good performance google says you need to achieve LCP within 2.5 sec. This can be identified using browser dev tools network tab water fall field.
`GOOD - 2.5 sec .... NEEDS IMPROVEMENT .... 4.0 SEC POOR`

#### How to improve ?
1. Reduce load time of resourced like images, videos by using low resolution based on screen size and bare minimum fonts 
2. Use a CDN for reources like html, css, javascript, images and videos possible
3. using rel="preload" attribute in link tags
    - using preload to load the critical resources that are required for critical rendering path of html can significantly improve the load time
    - browser can load the critical resource without parsing the whole html

### FID (First input delay)
The interactivitiy delay of a website, from the moment you click a button how long it takes to process ?
`GOOD - 100 ms .... NEEDS IMPROVEMENT .... POOR`

### CLS (Cumulative layout shift)
It measures Visual stabality. The elements on a website should not be jumping around in unexpected way. Using images without dimensions can create a bad CLS score

`Note: Unlighthouse can be used to run lighthouse on all the pages of a website in parallel`
