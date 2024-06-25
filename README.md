这周完成了主要的课表显示功能，介绍如下：
数据初始化和页面加载：在 onLoad 生命周期中，获取系统信息，初始化页面宽度，并调用 getWeekDates、getNowWeek、getData 和 getTodayDate 方法来获取并设置页面所需的日期、周数、课程数据和当前日期信息。
周数切换功能：通过 selectWeek 方法显示选择周数的弹窗，用户可以选择不同的周数，切换到指定的周数并更新课表显示。使用 switchWeek 和 switchWeekFn 方法来处理用户选择的周数切换操作，getWeekDates 方法根据选择的周数计算并更新本周的日期列表。
课程数据和更新：通过 getData 方法从本地缓存获取课程数据，如果存在缓存则直接使用缓存数据，并构建课程颜色映射关系。如果没有缓存或者需要强制更新 (updateFn(true))，则调用 updateFn 方法从服务端获取最新的课程数据，并更新本地缓存。
课程显示和样式：使用 swiper 组件实现周数切换，每个 swiper-item 对应一个周数，通过 wx:if 控制课程是否显示在当前周，使用 bindtap 方法绑定点击事件以导航到课程详情页。课程的具体位置和背景色由 style 属性动态计算和设置。
实现了一个完整的小程序课表显示页面，包括切换周数、更新课程数据、显示课程信息和样式控制等功能。通过调用服务端接口获取课程数据，并使用本地缓存优化加载速度和用户体验。
