# copper

            Type: Number
            Default: 0
            Options: 0,1,2,3
            这个具体每个值对应的效果我也不是很清楚，推荐在上面的官方示例里都试一试，我都是比较喜欢2。
            
            dragMode
            Type: String
            Default: 'crop'
            Options:
            
            'crop'： 在裁剪框外拖动鼠标会生成一个新的裁剪框。
            'move'： 在裁剪框外拖动鼠标会移动原图。
            'none'： 在裁剪框外拖动鼠标则什么也不做。
            aspectRatio
            Type: Number
            Default: NaN
            这个是裁剪框的纵横比，默认是不限制的。例如1:1的头像就写1,16:9可写成16 / 9。
            
            data
            Type: Object
            Default: null
            The previous cropped data if you had stored, will be passed to setData method automatically.
            
            （没怎么用过，都是直接用setData方法）
            
            preview
            Type: String (jQuery selector)
            Default: ''
            预览图的位置，用jQuery选择器表示。
            
            responsive
            Type: Boolean
            Default: true
            在更改窗口大小后是否重新渲染cropper。
            
            restore
            Type: Boolean
            Default: true
            在更改窗口大小后是否恢复裁剪区域。
            
            checkCrossOrigin
            Type: Boolean
            Default: true
            检查图像是否是跨域图像。（具体查看官方文档）
            
            checkOrientation
            Type: Boolean
            Default: true
            （具体查看官方文档）
            
            modal
            Type: Boolean
            Default: true
            非裁剪区域是否用黑罩遮盖。
            
            guides
            Type: Boolean
            Default: true
            裁剪区域是否显示虚线。
            
            center
            Type: Boolean
            Default: true
            裁剪区域正中央是否显示+号。
            
            highlight
            Type: Boolean
            Default: true
            裁剪区域是否高亮显示。
            
            background
            Type: Boolean
            Default: true
            是否显示背景的黑白方格（类似PS里透明图层的显示方式）。
            
            autoCrop
            Type: Boolean
            Default: true
            cropper初始化完成后是否自动显示裁剪框
            
            autoCropArea
            Type: Number
            Default: 0.8 (80% of the image)
            自动显示的裁剪框的大小。因此，数字应当在0~1之间。
            
            movable
            Type: Boolean
            Default: true
            是否允许移动原图。（如果这里填false那么尽管dragMode的值是move，在裁剪框外拖动也不会移动原图）
            
            rotatable
            Type: Boolean
            Default: true
            是否可以旋转原图。
            
            scalable
            Type: Boolean
            Default: true
            是否可以对原图进行纵横拉伸。
            
            例如把原图宽度拉长为原来的2倍或者拉长为原来的-1倍（即水平翻转）。
            
            zoomable
            Type: Boolean
            Default: true
            是否可以对原图进行缩小放大。
            
            zoomOnTouch
            Type: Boolean
            Default: true
            是否允许在移动端上使用双指触摸缩放原图。
            
            zoomOnWheel
            Type: Boolean
            Default: true
            是否允许使用鼠标滚轮缩放原图。
            
            wheelZoomRatio
            Type: Number
            Default: 0.1
            当使用鼠标滚轮缩放时的比例。
            
            cropBoxMovable
            Type: Boolean
            Default: true
            是否允许移动裁剪框。
            
            cropBoxResizable
            Type: Boolean
            Default: true
            是否允许通过拖动裁剪框的边框来调整裁剪框的大小。
            
            toggleDragModeOnDblclick
            Type: Boolean
            Default: true
            是否允许通过双击来在crop和move之间切换dragMode。
            
            minContainerWidth
            Type: Number
            Default: 200
            容器宽度最小值。
            
            minContainerHeight
            Type: Number
            Default: 100
            容器高度最小值。
            
            minCanvasWidth
            Type: Number
            Default: 0
            canvas（原图）宽度最小值。
            
            minCanvasHeight
            Type: Number
            Default: 0
            canvas（原图）高度最小值。
            
            minCropBoxWidth
            Type: Number
            Default: 0
            剪切框宽度最小值。
            
            Note: This size is relative to the page, not the image.
            
            minCropBoxHeight
            Type: Number
            Default: 0
            剪切框高度最小值。
            
            Note: This size is relative to the page, not the image.
            
            ready
            Type: Function
            Default: null
            A shortcut of the "ready" event.
            
            cropstart
            Type: Function
            Default: null
            A shortcut of the "cropstart" event.
            
            cropmove
            Type: Function
            Default: null
            A shortcut of the "cropmove" event.
            
            cropend
            Type: Function
            Default: null
            A shortcut of the "cropend" event.
            
            crop
            Type: Function
            Default: null
            A shortcut of the "crop" event.
            
            zoom
            Type: Function
            Default: null
            A shortcut of the "zoom" event.
            
            常用方法
            除了"setAspectRatio","replace"和"destroy"以外，所有的方法都要在ready后才能使用。这里只介绍几个常用的方法，全部的方法请到官方文档查阅。
            
            方法的使用格式为
            
            $().cropper('method',arg0,arg1,arg2,...);
            crop()
            手动显示裁剪框。
            
            $().cropper({
              autoCrop: false,
              ready: function () {
                // Do something here
                // ...
            
                // And then
                $(this).cropper('crop');
              }
            });
            reset()
            恢复全部到初始状态。
            
            replace(url[, onlyColorChanged])
            url:
            
            Type: String
            A new image url.
            onlyColorChanged (optional):
            
            Type: Boolean
            If only change the color, not the size, then the cropper only need to change the srcs of all related images, not need to rebuild the cropper. This can be used for applying filters.
            If not present, its default value is false.
            替换cropper中的图像文件，通常第二个参数不管。
            
            destroy()
            销毁cropper，并且会移除img标签的src属性的值。
            
            getCroppedCanvas([options])
            options (optional):
            
            Type: Object
            Properties:
            
            width: the destination width of the output canvas.
            height: the destination height of the output canvas.
            minWidth: the minimum destination width of the output canvas, the default value is 0.
            minHeight: the minimum destination height of the output canvas, the default value is 0.
            maxWidth: the maximum destination width of the output canvas, the default value is Infinity.
            maxHeight: the maximum destination height of the output canvas, the default value is Infinity.
            fillColor: a color to fill any alpha values in the output canvas, the default value is transparent.
            imageSmoothingEnabled: set to change if images are smoothed (true, default) or not (false).
            imageSmoothingQuality: set the quality of image smoothing, one of "low" (default), "medium", or "high".
            (return value):
            
            Type: HTMLCanvasElement
            A canvas drawn the cropped image.
            Notes:
            
            输出的canvas的纵横比会自动适应于裁剪框的纵横比.
            如果打算得到JPEG图像，那么应该先设置fillColor参数，否则裁剪后的透明部分默认会由黑色填充。
            Browser support:
            
            Basic image: requires Canvas support (IE 9+).
            Rotated image: requires CSS3 2D Transforms support (IE 9+).
            Cross-origin image: requires HTML5 CORS settings attributes support (IE 11+).
            得到裁剪到的图像的canvas，如果没有裁剪，那么就返回的是整个原图图像的canvas。
