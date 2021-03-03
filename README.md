# Computer-Vision-Merchandising-Resets

## Background
This was a simple research project that I created to fulfil a requirement for my Computer Vision class. The premise was to apply computer vision to whatever domain I desired. I chose the retail domain. Particularly, I was interested in how computer vision could be applied to merchandising resets, a process that take place in retail businesses to update inventory. While many different retail actions can constitute a 'reset' I chose the definition that more closely aligned itself with the work that I did as a retail merchandiser. 
One such process was checking shelves for UPC tags and their respective products. Being able to ascertain the status of both of these objects allow the merchandiser to understand whether or not the product is (a) in-stock, (b) out-of-stock, (c) misplaced, or (d) discontinued. From a programming perspective, it seems perfectly feasible that such a task can be easily automated.

## Hypotheses
However, I chose to focus my efforts on illustrating the potentiality of computer vision with respects to the rudimentary processes of computer vision, namely barcode and image detection. After conducting research on different computer vision developments made in the retail domain, I decided that I would build upon an existing algorithm for barcode detection, and also to test how various hypotheses that I had about different aspects about the process. Specifically I chose Tunistra's Algorithm and decided to incorporate a noise-removal function in the process.
As for the aforementioned hypotheses, I had several.

1) Product-wise detection is inefficient in comparison to category-wise detection.
2) The nature (size, shape, etc.) of the UPC tag affects accuracy of the model.
3) Noise-removal during image-processing can increase accuracy of the model.
4) Noise-removal during training can increase the accuracy of the model.
