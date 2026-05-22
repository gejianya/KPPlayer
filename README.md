# KPPlayer
### 播放器描述：
KPPlayer（全名K-Pop-Media-Player），是一款多功能视频播放器和海报墙影视管理中心，独有的横屏转竖屏播放功能和播放器内视频批量移动、删除管理功能、视频无损裁剪，庞大的用户自建数据库中心让成千上万视频转桌面动态壁纸播放模式亦是其特色之一，让K- POP舞台和各类影视元数据在该播放器中得到完美的呈现。


### 部分功能列表：

1. **桌面端海报墙首页**
    - 设计类似流媒体首页的海报墙浏览模式，支持大批量影片卡片展示、封面加载、标题、番号、年份、演员等关键信息展示。
    - 设计多维筛选体系，包括合集、厂牌、年份、类型、标签、观看状态、番号首字母等筛选维度。
    - 增加首页排序能力，支持按番号、标题、文件名、发行日期、播放次数、分辨率、体积、评分、播放时长、随机等方式排序。
    - 设计排序记忆能力，用户上次选择的排序方式和升降序会在下次打开应用时自动保留。
    - 设计首页懒加载机制，大规模媒体库下分批加载卡片，避免一次性渲染造成性能压力。
    - 设计顶部推荐区域，用于从当前媒体库中展示推荐海报，提升首页视觉层级和浏览效率。
      
2. **桌面端详情页**
    - 设计影片详情页，整合封面、标题、发行日期、时长、分辨率、分级、评分、体积、观看状态、播放进度、导演、制作方等信息。
    - 优化详情页胶囊 UI，将时长、体积、观看状态等关键信息做成高识别度标签。
    - 设计无效字段隐藏规则，如导演未填写、评分未填写、体重为空等字段不展示，减少页面干扰。
    - 设计演员表模块，点击演员头像可进入演员作品页，并支持演员收藏状态反馈。
    - 设计预览图区域、同系列推荐、相关类型影片、猜你喜欢等横向内容区，增强详情页的探索路径。
    - 设计系列、类型、标签、发行商等信息区域，支持点击胶囊进入对应筛选作品页。
      
3. **演员作品页与演员信息页**
    - 设计从首页演员入口和详情页演员头像入口进入的演员作品页，展示该演员全部作品。
    - 设计演员资料卡，整合头像、出生日期、年龄、出生地、血型、身高、体重、三围、出道、出演期间、专属、其他活动、外部链接等信息。
    - 解析演员资料 JSON 中的综合字段，从长文本中提炼有效信息，并对空值字段进行隐藏。
    - 优化字段命名，将日文/繁体表达转为更适合中文用户阅读的简体中文字段。
    - 统一演员作品页的批量选择能力，支持点选、框选、Shift 连选、全选本页、反选本页、清空选择、批量移动、批量删除。
    - 设计演员收藏交互，确保收藏后在演员页和详情页演员头像上都有明确 UI 反馈。
      
4. **系列页与类型/标签/发行商筛选页**
    - 设计系列作品页，支持从首页系列入口和详情页系列字段进入。
    - 设计类型、标签、系列、发行商筛选结果页，统一使用演员作品页同款视觉样式和分页器。
    - 优化筛选页从原始黑色粗糙页面升级为统一背景、统一卡片、统一分页体验。
    - 修复筛选结果不完整的问题，确保结果页可以显示全部匹配作品，而不是只显示部分卡片。
    - 将筛选页作品排序从番号字母序调整为按发行时间从晚到早，更符合用户浏览作品的习惯。
      
5. **播放器与播放列表**
    - 设计视频播放页，支持播放、暂停、上一个、下一个、快进 30 秒、快退 30 秒、删除当前视频、打开当前路径等操作。
    - 播放器支持市面上几乎所有的视频格式，包括mp4、webm、mkv、avi、wmv、rmvb、flv、m4v、mov、ts、mpg、asf、mpeg、ogv、f4v、m2ts等常见格式，集成FFmpeg 与 video toolbox硬件加速。
    - 设计播放器支持竖屏播放模式、正常横屏播放模式、壁纸播放模式三种视频播放模式，其中竖屏播放模式支持将横屏视频转竖屏播放；壁纸模式支持将视频变为系统动态壁纸，即可以把视频作为桌面壁纸进行播放，同时有声音，动态画面，支持快进快退，支持真实随机播放，支持切换视频，支持壁纸模式下的视频删除功能，支持视频画面区域放大功能。
    - 设计顶部菜单栏和右键菜单的统一顺序，保证不同入口的操作一致。
    - 增加快捷键能力，如 PgUp 切换上一个视频、PgDn 切换下一个视频。
    - 设计播放列表默认隐藏，用户点击后再展示，避免初始加载时占用过多资源。
    - 设计播放列表滚动加载机制，默认只显示前 100 个视频，滚动到底后每次继续加载后 100 个。
    - 设计播放中自动预加载列表机制，当当前播放位置接近已加载列表末尾时，自动加载后续视频，避免播放到第 100 个后断档。
    - 设计播放记录体系，记录已观看、观看至某时间点、播放次数等状态。
      
6. **分集/续集播放逻辑**
    - 针对多分集影片设计主体番号聚合逻辑，例如 svdvd-310-CD1/CD2/CD3、svdvd-310-1/2/3、svdvd-310-01/02/03、svdvd-310-a1/a2/a3 等都识别为同一作品的分集。
    - 设计详情页播放规则：首次播放必须从第 1 集开始，播放完第 1 集后继续第 2 集，直到该作品所有分集播放完成后才进入下一个作品。
    - 设计续播规则：如果某个分集处于观看中，下次点击详情页播放时从对应分集和对应进度继续。
    - 保持随机播放模式不受影响，避免为了分集规则破坏用户原有随机播放习惯。
      
7. **后台媒体管理能力**
    - 设计本地媒体库管理，支持新建媒体库、选择本地文件夹、全量扫描、刷新海报墙、清空筛选、清空缓存等操作。
    - 设计媒体文件扫描逻辑，读取视频文件、封面、NFO、演员、标签、系列、厂牌、发行日期等元数据。
    - 设计 SQLite 本地数据库结构，用于管理视频、媒体库、演员、系列、标签、播放记录、缓存等数据。
    - 设计播放次数不直接写入视频主表，而是写入观看记录文件，便于统一管理已观看、观看进度和播放次数。
    - 设计 NFO 读取与展示规则，将 <genre>、<tag>、<series>、<publisher> 等字段分别展示到对应区域，并去除重复的“系列:”标签。
      - 设计媒体文件移动、删除、批量移动、批量删除等文件管理能力。
      
8. **NAS模式与本地模式双路径能力**
    - 在不破坏本地模式的前提下，设计独立 NAS 全局模式。
    - 设计底层资源访问分层：上层页面保持一套，底层通过本地资源适配器和 NAS SMB 资源适配器分叉。
    - 设计 NAS 连接、共享盘浏览、NAS 文件夹选择、NAS 数据库创建、NAS 媒体扫描等流程。
    - 设计 NAS 模式下的路径管理规则，避免本地 Finder 路径和 NAS 路径混用。
    - 设计 NAS 模式下的播放、图片读取、删除、移动、打开路径、裁剪等路径敏感功能。
    - 推动 NAS 模式从“能连接”迭代到“可作为真实媒体库使用”。

9. **移动端app/小屏适配体验**
    - 针对小屏设备设计更适合触控和窄屏浏览的页面布局。
    - 优化移动端播放器、播放列表、海报卡片、详情信息区域的展示方式。
    - 控制移动端一次性渲染数量，避免大量视频列表在小屏设备上造成卡顿。
    - 对关键操作按钮进行移动端适配，让播放、切换、列表展示等核心操作保持可用。
    - 在桌面端与移动端之间保持信息结构一致，减少用户跨设备使用成本。
      
10. **批量管理与多选交互**
    - 设计多选管理模式，支持进入/退出多选。
    - 支持视频文件批量删除和批量移动，可以在播放器中将一个或无数个视频文件夹移动到其他位置，同时自动同步到数据库和海报墙数据中，极大增强了该播放器的文件批量自动管理能力。适用于海报墙首页、演员作品页、筛选结果页等多个页面。
    - 支持点选、框选、Shift 连选、全选本页、反选本页、清空选择。
    - 支持批量删除和批量移动，适用于海报墙首页、演员作品页、系列作品页、筛选结果页等多个页面。
    - 设计多选状态下的卡片遮罩和“选择”按钮，让用户明确当前卡片是否可选、是否已选。
    - 统一不同页面的多选交互逻辑，减少重复学习成本。
      
11. **异常状态与问题修复机制**
    - 解决演员页收藏按钮点击后无即时反馈的问题，保证收藏/取消收藏状态能在当前页面实时显示。
    - 解决详情页无效字段展示问题，隐藏“未填写”“―kg”等无意义信息。
    - 解决筛选页样式粗糙、背景不统一、结果展示不完整的问题。
    - 解决首页排序中分辨率、标题、文件名等排序逻辑不准确的问题。
    - 解决新建数据库全量扫描后顶部推荐区为空的问题，重新梳理推荐区数据来源。
    - 解决横向推荐列表右侧箭头不显示的问题，按实际可视区域与内容宽度判断是否显示箭头。
    - 解决播放列表只加载前 100 个、不继续滚动加载的问题。
    - 解决多分集视频播放顺序错误、播放完跳到其他作品的问题。
    - 解决 NAS 模式下图片加载、播放起播、快进快退、路径打开、删除移动等链路中的多项稳定性问题。
      
12. ...视频无损裁剪等更多功能等待你自己发掘。


### 产品由来：
本项目是我个人使用ChatGPT GPT5.4-5.5模型，通过codex工具从0到1独立设计制作。项目构建最初是为了使用竖屏功能播放横屏K-POP舞台视频，之后一步步丰富功能和架构到目前的完整产品形态。

这个项目不是我为了展示代码能力做的（当然我以前也学习过iOS开发和C语言，有部分代码基础），而是为了训练和验证自己作为产品经理从真实痛点出发，把需求持续拆解、验证和迭代的能力。AI 承担了部分工程实现，我主要负责市场调研、需求收集、问题定义、产品方案、所有产品和功能设计、交互逻辑、优先级、验收标准和真实使用反馈闭环。

该项目从构思-立项-项目架构设计-需求沟通-深度结合ai编程-测试-用户体验-优化与bug解决-不断添加新功能-最终产出可用产品，耗时3月有余。项目拥有桌面端app（macOS和win11双平台）、web浏览器访问、本地和NAS双模式、独立的移动端app（已做好但暂未上线，因没有iOS个人开发者账号，暂无法上架AppStore）、前端和后端深度开发融合、后端上万媒体资源管理能力、海报墙瀑布流展示、前端页面设计、视频播放直流、转码缓冲设计、文件批量移动删除、横屏转竖屏播放、视频画面移动和放大、视频转桌面动态壁纸播放、视频无损裁剪等独有功能。

该项目是我个人从0到1独立定义本地媒体库管理核心场景，拆解海报墙浏览、详情页、演员/系列聚合、筛选排序、播放记录、批量管理等功能模块。设计复杂资源管理流程，覆盖本地文件、NAS SMB 资源、NFO 元数据、演员信息、图片缓存、播放进度等多类数据对象。通过 AI 协作完成可运行桌面端 Demo，并持续基于真实使用反馈优化体验，包括分页懒加载、播放列表滚动加载、分集顺序播放、详情页信息展示、批量选择与删除移动等。建立问题验收机制，对图片加载、播放续播、NAS 访问、文件删除/移动、无损裁剪功能等高风险链路进行黑盒验证，推动产品从“能用”迭代到“稳定可用”。

本人目前处于离职状态，正在寻求AI 产品经理 / AI 应用产品经理、工具型产品经理 / 内容类产品经理、客户端产品经理 / 桌面端（或移动端）app产品经理、B 端/中后台产品经理职位。如果你看到这个项目觉得我目前部分产品能力符合贵公司产品经理职位要求，欢迎邮件联系我：jianya.ge@outlook.com，我会第一时间发送简历给您。


### 当前版本：
因为本人使用的是MacBook Air M4和arm64版win11虚拟机构建的Macos版app和exe文件，因此macos版本app肯定是支持M系列芯片的Macos系统安装使用，非M系列芯片的macOS系统可以下载安装尝试，但不保证一定能正常使用，因为我没有相应的电脑进行测试。而windows系统下的exe版本是支持arm64位win11系统进行安装使用，而win10系统和非arm64位版本则不能保证一定能安装使用。

同时移动端iOS版本app已经设计和开发完成，但是本人没有iOS个人开发者账号（主要是太贵），因此无法上架苹果官方App Store，所以暂时先不上线。
如果macOS版本安装时被系统拦截提示未知应用不允许安装，请打开设置并选择允许从任何来源安装应用。


### 是否开源：
项目最终选择不开源，目的是防止某些公司、团队或个人利用开源代码只修改某些地方甚至不修改直接进行商用或售卖。


### 版权声明：
Copyright © 2026 gejianya. All rights reserved.  
本软件仅允许个人非商业使用，未经授权禁止复制、修改、反向工程、二次分发或商业销售。


下面是更适合 GitHub / 产品介绍 / 英文项目页使用的专业英文版本：


## English Version

### Product Description

KPPlayer, short for K-Pop Media Player, is a multifunctional video player and poster-wall media management center. It features a unique landscape-to-portrait playback mode, in-player batch video moving and deletion, lossless video trimming, and a powerful user-managed local media database.

With its large-scale self-built media library system, KPPlayer can manage thousands of videos and turn them into dynamic desktop wallpaper playback sessions. It is designed to present K-Pop stage videos and various media metadata in a rich, organized, and highly visual way.

---

### Key Features

#### 1. Desktop Poster Wall Home Page

- Designed a streaming-style poster wall browsing experience with support for large-scale media card rendering, cover loading, titles, media codes, years, actors, and other key metadata.
- Built a multi-dimensional filtering system, including collections, labels/studios, years, genres, tags, watch status, and media-code initials.
- Added homepage sorting by media code, title, filename, release date, play count, resolution, file size, rating, runtime, and random order.
- Implemented sorting memory so the latest selected sorting field and direction are automatically restored the next time the app is opened.
- Designed lazy loading for large media libraries to reduce rendering pressure and improve performance.
- Added a top recommendation section to highlight selected posters from the current media library and improve browsing efficiency.

#### 2. Desktop Detail Page

- Designed a video detail page integrating cover art, title, release date, runtime, resolution, rating, file size, watch status, playback progress, director, production studio, and other metadata.
- Optimized capsule-style metadata UI for key fields such as runtime, file size, and watch status.
- Added rules to hide invalid or empty fields, such as missing director, missing rating, or empty body-weight values, to reduce visual noise.
- Designed an actor list module where users can click actor avatars to enter actor-specific work pages, with clear favorite-state feedback.
- Added preview images, same-series recommendations, related-genre videos, and personalized recommendation rows to improve content discovery.
- Designed clickable capsule areas for series, genres, tags, and publishers, allowing users to navigate to corresponding filtered work pages.

#### 3. Actor Works Page and Actor Profile Page

- Designed actor work pages accessible from both the homepage actor entry and actor avatars on the detail page.
- Designed actor profile cards with avatar, birth date, age, birthplace, blood type, height, weight, measurements, debut year, active period, exclusive studio, other activities, and external links.
- Parsed actor profile JSON overview fields, extracted useful structured information from long text, and hid empty fields.
- Optimized field naming by converting Japanese or Traditional Chinese expressions into Simplified Chinese labels better suited for Chinese users.
- Unified batch selection capabilities on actor work pages, supporting click selection, box selection, Shift multi-select, select current page, invert current page, clear selection, batch move, and batch delete.
- Designed actor favorite interactions so favorite and unfavorite states are immediately reflected on both actor pages and detail-page actor avatars.

#### 4. Series Pages and Genre / Tag / Publisher Filter Pages

- Designed series work pages accessible from both the homepage series entry and series fields on the detail page.
- Designed filter result pages for genres, tags, series, and publishers, using the same visual style and pagination system as actor work pages.
- Upgraded the original rough black-background filter pages into a unified layout with consistent background, cards, and pagination.
- Fixed incomplete filter result rendering so all matched works can be displayed instead of only a partial set of cards.
- Changed filtered result sorting from media-code alphabetical order to release date descending, which better matches browsing behavior.

#### 5. Video Player and Playlist

- Designed a video playback page supporting play, pause, previous, next, forward 30 seconds, rewind 30 seconds, delete current video, and open current path.
- Supports almost all common video formats, including MP4, WebM, MKV, AVI, WMV, RMVB, FLV, M4V, MOV, TS, MPG, ASF, MPEG, OGV, F4V, and M2TS, with FFmpeg and VideoToolbox hardware acceleration integration.
- Designed three playback modes: portrait mode, standard landscape mode, and wallpaper mode.
- Portrait mode supports converting landscape videos into portrait-style playback.
- Wallpaper mode allows videos to be played as dynamic desktop wallpapers with audio, motion visuals, seek controls, real random playback, video switching, video deletion, and zoom-crop support.
- Unified the order of the top menu bar and context menu to keep operations consistent across different entry points.
- Added keyboard shortcuts such as PgUp for previous video and PgDn for next video.
- Designed the playlist to be hidden by default and displayed only when the user opens it, reducing initial resource usage.
- Implemented playlist incremental loading: the first 100 videos are loaded by default, and another 100 videos are loaded each time the user scrolls near the bottom.
- Added automatic preloading for the playback list when the current playing item approaches the end of the loaded list, preventing playback gaps.
- Designed a watch-record system to track watched status, playback position, and play count.

#### 6. Multi-Part / Episode Playback Logic

- Designed media-code grouping logic for multi-part videos, recognizing formats such as `svdvd-310-CD1/CD2/CD3`, `svdvd-310-1/2/3`, `svdvd-310-01/02/03`, and `svdvd-310-a1/a2/a3` as episodes of the same work.
- Designed detail-page playback rules so first-time playback starts from episode 1, continues through the remaining episodes, and only moves to the next work after all episodes are completed.
- Designed resume rules so if an episode is partially watched, the next playback starts from the corresponding episode and timestamp.
- Kept random playback unaffected to avoid breaking the user’s existing random-play behavior.

#### 7. Backend Media Management

- Designed local media library management, including creating media libraries, selecting local folders, full scanning, refreshing the poster wall, clearing filters, and clearing cache.
- Designed media scanning logic to read video files, covers, NFO files, actors, tags, series, studios, release dates, and other metadata.
- Designed a local SQLite database structure to manage videos, media libraries, actors, series, tags, playback records, and caches.
- Designed play counts to be stored in watch-record files rather than directly in the main video table, making watched status, playback progress, and play count easier to manage together.
- Designed NFO reading and display rules, mapping `<genre>`, `<tag>`, `<series>`, and `<publisher>` fields into separate UI sections while removing duplicated `series:` tag entries.
- Designed file management capabilities including move, delete, batch move, and batch delete.

#### 8. Dual Local / NAS Mode

- Designed an independent global NAS mode without breaking the existing local mode.
- Designed a layered resource-access architecture: the upper UI remains unified, while the bottom resource layer branches into a local resource adapter and a NAS SMB resource adapter.
- Designed NAS connection, shared-folder browsing, NAS folder selection, NAS database creation, and NAS media scanning flows.
- Designed NAS path-management rules to prevent local Finder paths and NAS paths from being mixed.
- Adapted path-sensitive features for NAS mode, including playback, image reading, deletion, moving, path opening, and trimming.
- Iterated NAS mode from basic connectivity into a practical media-library mode suitable for real usage.

#### 9. Mobile App and Small-Screen Adaptation

- Designed layouts optimized for touch interaction and narrow-screen browsing.
- Optimized the mobile player, playlist, poster cards, and detail information sections.
- Controlled the number of items rendered at once on mobile devices to prevent performance issues with large video lists.
- Adapted key action buttons so core operations such as play, switch video, and show playlist remain usable on small screens.
- Maintained consistent information architecture across desktop and mobile to reduce cross-device learning costs.

#### 10. Batch Management and Multi-Select Interaction

- Designed a multi-select management mode with enter and exit states.
- Supported batch deletion and batch moving of video files. Users can move one or many video folders to other locations directly inside the player, while automatically syncing database and poster-wall data.
- Supported click selection, box selection, Shift multi-select, select current page, invert current page, and clear selection.
- Applied batch delete and batch move across the poster wall homepage, actor work pages, series pages, and filter result pages.
- Designed card overlays and “Select” buttons in multi-select mode so users can clearly see whether a card is selectable or selected.
- Unified multi-select interaction logic across different pages to reduce learning cost.

#### 11. Error Handling and Issue Resolution

- Fixed the issue where the actor favorite button had no immediate feedback on the actor page.
- Fixed meaningless invalid fields such as “not filled” and “―kg” being displayed on detail and actor pages.
- Fixed rough filter page styling, inconsistent background, and incomplete result rendering.
- Fixed incorrect sorting logic for resolution, title, filename, and other homepage sorting options.
- Fixed the empty top recommendation section after creating and fully scanning a new database.
- Fixed horizontal recommendation arrows not showing correctly by recalculating visibility based on actual visible area and content width.
- Fixed playlist loading only the first 100 videos without continuing to load more.
- Fixed incorrect multi-part video playback order and the issue where playback jumped to another work before all episodes were completed.
- Fixed multiple NAS-mode stability issues involving image loading, startup playback, seek performance, path opening, deletion, moving, and related resource chains.

#### 12. More Features

Additional features such as lossless video trimming and other advanced media-management capabilities are available for users to explore.

---

### Project Origin

This project was independently designed and built from scratch by me with ChatGPT and Codex as AI development partners. The original purpose was to solve a personal need: playing landscape K-Pop stage videos in a portrait-style viewing mode. Over time, the project evolved step by step into a complete desktop media player and media-management product.

This project was not created primarily to showcase coding skills, although I have previously studied iOS development and C and have some programming foundation. Its main purpose was to train and validate my ability as a product manager to identify real user pain points, break down requirements, design solutions, verify outcomes, and continuously iterate based on actual usage.

AI handled part of the engineering implementation. I was mainly responsible for market research, requirement collection, problem definition, product planning, feature design, interaction logic, prioritization, acceptance criteria, and the full feedback loop from real usage.

The project took more than three months from concept, project initiation, architecture planning, requirement communication, AI-assisted development, testing, user-experience optimization, bug fixing, continuous feature expansion, and final delivery of a usable product.

The product currently includes a desktop app for macOS and Windows 11, browser-based web access, local and NAS dual modes, and an independent mobile app that has already been designed and developed but is not yet available on the App Store due to the lack of an Apple individual developer account.

It combines frontend and backend development, large-scale media resource management, poster-wall waterfall browsing, frontend UI design, direct video streaming, transcoding and buffering design, batch file moving and deletion, landscape-to-portrait playback, video zoom and positioning, dynamic desktop wallpaper playback, lossless video trimming, and other distinctive features.

This project represents my personal end-to-end product practice: independently defining the core scenario of local media-library management, breaking it down into modules such as poster-wall browsing, detail pages, actor and series aggregation, filtering and sorting, playback records, and batch management.

I designed complex resource-management flows covering local files, NAS SMB resources, NFO metadata, actor information, image cache, playback progress, and multiple other data objects. Through AI collaboration, I completed a runnable desktop demo and continuously optimized the user experience based on real feedback, including paginated lazy loading, playlist incremental loading, multi-part sequential playback, detail-page information display, batch selection, deletion, and moving.

I also established an issue acceptance and verification process, performing black-box testing on high-risk flows such as image loading, playback resume, NAS access, file deletion and moving, and lossless trimming. This helped push the product from “usable” to “stable and practical.”

I am currently available for new opportunities and looking for roles such as AI Product Manager, AI Application Product Manager, Tool Product Manager, Content Product Manager, Client-side Product Manager, Desktop or Mobile App Product Manager, and B2B / Admin System Product Manager.

If you find this project relevant to your company’s product-management needs, feel free to contact me by email: jianya.ge@outlook.com. I will send my resume as soon as possible.

---

### Current Version

Because the current builds were created on a MacBook Air M4 and an ARM64 Windows 11 virtual machine, the macOS version is expected to support Apple Silicon Macs. Intel-based macOS devices may try installing it, but compatibility is not guaranteed because I do not have the corresponding hardware for testing.

The Windows installer currently supports ARM64 Windows 11. Windows 10 and non-ARM64 Windows versions are not guaranteed to install or run correctly.

The iOS mobile app has also been designed and developed, but I do not currently have an Apple individual developer account, so it has not been published on the official App Store.

If macOS blocks installation because the app is from an unidentified developer, you may need to allow the app manually in macOS Privacy & Security settings.

---

### Open Source Policy

This project is not open source. The purpose is to prevent companies, teams, or individuals from reusing the source code for commercial resale or distribution with only minor changes or no changes at all.

---

### Copyright Notice

Copyright © 2026 gejianya. All rights reserved.

This software is permitted for personal, non-commercial use only. Unauthorized copying, modification, reverse engineering, redistribution, or commercial sale is prohibited.


