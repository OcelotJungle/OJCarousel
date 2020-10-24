# OJCarousel
Simple lightweight JS image carousel. Requires jQuery.<br/>
You can copy, modify and use it where do you want and as do you want.<br/><br/>

How to use:<br/>
1. You need to wrap your slides and previous/next buttons into an element (for example, #carousel).<br/>
2. Just type "let carousel = new OJCarousel(config)".<br/>
3. Config is an object containing carousel's properties (square brackets show the default value): <br/>
    carouselSelector - CSS selector of carousel's wrapper element. ["#carousel"]<br/>
    slideSelector - CSS selector of carousel's slides. [".slide"]<br/>
    defaultActive - an index of default active (from 0). [0]<br/>
    mobileDragBorder - a percentage of mobile display's width after which carousel will start dragging. [0.2]<br/>
    doAutoMove - should carousel auto move or no. [true]<br/>
    slideTimeout - time in ms between auto slide moves. [6000]<br/>
    pauseTimeout - time in ms after which carousel starts auto moving (after dragging or switching slide by buttons). [5000]<br/>
    animationTimeout - time in ms that indicates how long does moving animation happens. [600]<br/>
    dragCursor - name of cursor that will be enabled when dragging. ["grabbing"]<br/>
    undragCursor - name of cursor that will be enabled when dragging stopped. [""] (sets default)<br/>
    height - height of the carosel. [$(window).height()]<br/>
    previousSlideButtonSelector - CSS selector of carousel's previous slide button (or, maybe, buttons). ["#previous-slide-btn"]<br/>
    nextSlideButtonSelector - CSS selector of carousel's next slide button (or, maybe, buttons). ["#next-slide-btn"]<br/>
    fallPercentagePreprocessor and movePercentagePreprocessor - functions that preprocess percents when slides falling (after drag) or moving (auto or buttons). They get only one value - percentage, that can be in range [[-100; 0]; 0] when previous slide becomes active and in range [0; [0; 100]] when next slide becomes active. You can do anything with this percentage value and return new value.<br/>
      For example, you can:<br/>
        move faster at the start and slower at the end: "(x) => ((Math.abs(x) * 0.01) ** 0.5) * 100 * Math.sign(x)";<br/>
        move slower at the start and faster at the end: "(x) => ((Math.abs(x) * 0.01) ** 2) * 100 * Math.sign(x)";<br/>
        move with precise grading: "(x) => Math.floor(Math.abs(x) * 0.1) * 10 * Math.sign(x)";<br/>
  3.1. You can change all params, change some params or use it as is.<br/>
  3.2. If you need to change any field or function - just do it, all of them are not private.<br/>
  3.3. You can look into unminified code to understand any misunderstandings.<br/>
4. To start carousel, you need to use "carousel.start()".<br/>
5. To stop carousel, you can use 2 ways:<br/>
  5.1. "carousel.kill(params)" - it will absolutely stop the carousel, unbind any events and make it just a part of code.<br/>
    5.1.1. Params is object containing only two properties: clearTimeouts [true] and clearEvents [true].<br/>
  5.2. More flexible way is to use "carousel.stop()", "carousel.setCursor()" and off the ".carousel" events manually.<br/>
6. If you have questions - you can write me an email on ocelotjungle@yandex.ru.<br/>
