---
title: Microsoft Teams 會議室需求
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6b2b2684-8e9e-49ea-8c46-1c690964f982
ms.collection:
- M365-collaboration
description: 瞭解支援Microsoft Teams 會議室的需求，包括選擇適當的裝置、麥克風、喇叭、相機和顯示器。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fbebffcbde9d7e42280357e152355e6e1705b893
ms.sourcegitcommit: 726df9ecac561bda18e349a5adab9bc85e52844d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2022
ms.locfileid: "65761085"
---
# <a name="microsoft-teams-rooms-requirements"></a>Microsoft Teams 會議室需求

Microsoft Teams 會議室調整為不同的房間大小。 Teams 會議室根據會議室的大小和使用，使用各種經過認證的音訊和視訊周邊裝置。 您可以選取適合空間的右核心裝置和主機，結合麥克風、喇叭、攝影機和顯示器，將Microsoft Teams 會議室部署到任何大小的空格中，從大型會議空間和會議室往上插入小型空間。  您可以在[裝置展示](https://products.office.com/microsoft-teams/across-devices)中取得可用於設定會議室的所有經認證音訊和視訊週邊設備的完整集合。

本文摘要說明支援 Microsoft Teams 會議室所需的裝置部署和組態需求。

您的部署涉及建立和設定Teams 會議室的資源帳戶，如[部署Microsoft Teams 會議室中](rooms-deploy.md)所述。

請參閱：

- [根據您方案的授權選項：Microsoft Teams 會議室](rooms-licensing.md)

> [!NOTE]
> Microsoft Teams 會議室登入 Microsoft Teams、商務用 Skype Server 2019 或 商務用 Skype Server 2015，並可加入由這些服務所主持的會議。
>
> Microsoft Teams 會議室不支援舊版平台 (例如 Lync Server 2013)。 Microsoft Teams 會議室不支援由 21Vianet 或 DoD 環境營運的 Microsoft 365 或 Office 365。
>
> 如果您擁有內部部署 Exchange Server，則 Microsoft Teams 會議室需要使用 Exchange Server 2013 SP1 或更新版本。

## <a name="hardware-requirements"></a>硬體需求
硬體部署包含一系列 Microsoft Teams 會議室系統，結合經認證的音訊和視訊週邊設備，以及可將這些裝置整合在一起的纜線解決方案。  以下說明這些選項。

**支援的 Microsoft Teams 會議室系統**

所有目前的 Microsoft Teams 會議室裝置和套件組合可在[會議室系統產品展示](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=20&page=1&filterIds=)中取得。

  |主控台|處理器|RAM|磁碟|
  |:-----|:-----|:-----|:-----|
  |[Cres 括弧彈性 UC-M130-T 搭配 Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M130-T)|Core i5|8 GB |128 GB |
  |[Cres 括弧彈性 UC- B130-T 搭配 Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B130-T)|Core i5|8 GB |128 GB |
  |[Cres 括弧彈性 UC-B140-T 搭配 Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B140-T)|Core i5|8 GB |128 GB |
  [Cres 括住 UC-C140-T 搭配 Intel NUC](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C140-T)|Core i7|8 GB |128 GB|
  |[Cres 括弧彈性 UC-M150-T 搭配 Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M150-T)  + [CCS-UCA-MIC](https://www.crestron.com/Products/Audio/Microphones/Wired-Microphones/CCS-UCA-MIC-KIT)|Core i7|8 GB |128 GB |
  |[Cres 括弧彈性 UC-MX150-T 搭配 Intel NUC](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MX150-T)|Core i5|8 GB |128 GB |
   [Cres 括弧彈性 UC-B160-T 搭配 Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B160-T)|Core i7|8 GB |128 GB|
  |[Cres 括住 UC-C160-T 搭配 Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C160-T)|Core i7|8 GB|128 GB|
  |[Cres 括住 UC 簡報傳輸器 (UC-PR) 和 ASUS 電腦的 UC 彈性 UC-MMX30-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MMX30-T)|Core i5/i7|8 GB |128 GB |
  |[Cres 括住 UC 簡報傳輸器 (UC-PR) 和 ASUS PC 的 UC 彈性 UC-BX30-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-BX30-T)|Core i5/i7|8 GB |128 GB |
  |[Cres 括住 UC 簡報傳輸器 (UC-PR) 和 ASUS 電腦的 UC 彈性 UC-CX100-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-CX100-T)|Core i5/i7|8 GB |128 GB |
  |[Cres 括弧彈性 UC-B30-T 搭配 ASUS 電腦](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B30-T)|Core i5/i7|8 GB |128 GB |
   |[Cres 括住 UC-C100-T 搭配 ASUS 電腦](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C100-T)|Core i5/i7|8 GB |128 GB |
   |[Cres 括弧彈性 UC-M50-T 搭配 ASUS 電腦](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M50-T)|Core i5/i7|8 GB |128 GB |
   |[Cres括弧可搭配 ASUS 電腦使用 UC-M70-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M70-T)|Core i5/i7|8 GB |128 GB |
   |[Cres 括弧彈性 UC-MX50-T 搭配 ASUS 電腦](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MX50-T)|Core i5/i7|8 GB |128 GB |
   |[Cres 括弧彈性 UC-MX70-T 搭配 ASUS 電腦](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MX70-T)|Core i5/i7|8 GB |128 GB |
   |Cres}LEX UC-B30-T with Dell OPTIPLEX|Core i5|8 GB|128 GB|
   |Cres括弧在 UC-Bx30-T 搭配 Dell OPTIPLEX|Core i5|8 GB|128 GB|
   |Cres括弧以 UC-MM30-T 搭配 Dell OPTIPLEX|Core i5|8 GB|128 GB|
   |Cres括弧以 UC-MMX30-T 搭配 Dell OPTIPLEX|Core i5|8 GB|128 GB|
   |Cres}LEX UC-M50-T with Dell OPTIPLEX|Core i5|8 GB|128 GB|
   |Cres括弧下，使用 Dell OPTIPLEX UC-MX50-T|Core i5|8 GB|128 GB|
   |Cres}LEX UC-M70-T with Dell OPTIPLEX|Core i5|8 GB|128 GB|
   |Cres括弧以 UC-MX70-T 搭配 Dell OPTIPLEX|Core i5|8 GB|128 GB|
   |Cres括住 UC-C100-T 搭配 Dell OPTIPLEX|Core i5|8 GB|128 GB|
   |Cres括住 UC-CX100-T 搭配 Dell OPTIPLEX|Core i5|8 GB|128 GB|
  |[Cres括弧水銀迷你 UC-MM30-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MM30-T)|Core i5|8 GB |128 GB |
  |[Dell OptiPlex 7080 with Logitech TAP](https://www.dell.com/en-us/work/shop/cty/pdp/spd/optiplex-7080-xe-teams) | Core i7 |16 GB |128 GB|
  |[HP Elite Slice for Meeting Rooms G2](https://www8.hp.com/us/en/elite-family/elite-slice-for-meetings.html) |Core i5 |8 GB |128 GB |
  |[HP Elite Slice G2 Audio Ready with Microsoft Teams Rooms](https://store.hp.com/us/en/pdp/hp-elite-slice-for-meeting-rooms-g2-skype-room-systems-audio-ready?jumpid=cp_r12131_us/en/psg/elite_slice_for_meetings/product/shop-now-eliteslicemeeting-g2-audio) |Core i5 |8 GB |128 GB |
  |[HP Slice Partner Ready with Logitech TAP]( https://www.logitech.com/video-collaboration/partners/hp.html)|Core i5|8 GB|128 GB| 
  | Lenovo ThinkSmart Hub 500 |Core i5 |8 GB |128 GB |
  |[Lenovo ThinkSmart Hub](https://news.lenovo.com/pressroom/press-releases/new-thinksmart-hub-collaboration-solution-from-lenovo-helps-organizations-embrace-hybrid-working-model/) |Core i5 |8 GB |128 GB|
  |Lenovo ThinkSmart Core Kit |Core i5|8 GB|128 GB|
  |[使用 Intel NUC 進行登入點選](https://www.logitech.com/product/microsoft-rooms)|Core i5|8 GB |128 GB |
  |Logitech Tap and Intel Tiger Canyon NUC PC |Core i5|8 GB|128 GB|
  |配備 Lenovo Core Compute 的 Logitech TAP 主機 |Core i5|8 GB|128 GB|
  |[記錄點選和 Lenovo ThinkSmart Tiny](https://www.logitech.com/video-collaboration/partners/lenovo.html)|Core i5|8 GB |128 GB|
  |[Poly G10-T with Lenovo ThinkSmart Tiny](https://www.poly.com/us/en/products/video-conferencing/g/g10) |Core i5| 8 GB | 128 GB|
  |配備 Lenovo Thinksmart Core 的 Poly GC8 主機|Core i5|8 GB|128 GB|
  |Poly GC8 Console with Dell Optiplex 7080|Core i5|8 GB|128 GB|
  |[Yealink MVC300 with Intel NUC](https://www.yealink.com/products_154.html)|Core i5|8 GB |128 GB |
  |[Yealink MVC500 with Intel NUC](https://www.yealink.com/products_126.html)|Core i5|8 GB |128 GB |
  |[Yealink MVC800 with Intel NUC](https://www.yealink.com/products_125.html)|Core i5|8 GB|128 GB|
  |[Yealink MVC900 with Intel NUC](https://www.yealink.com/product/microsoft-teams-room-system-mvc900)|Core i5|8 GB|128 GB|
  |[Yealink MVC 300 II](https://www.yealink.com/product/microsoft-teams-room-system-mvc300II) |Core i5|8 GB | 128 GB|
  |[Yealink MVC400](https://www.yealink.com/product/microsoft-teams-room-system-mvc400)        |Core i5|8 GB | 128 GB|
  |[Yealink MVC 500 II](https://www.yealink.com/product/microsoft-teams-room-system-mvc500II) |Core i5|8 GB | 128 GB|
  |[Yealink MVC 800 II](https://www.yealink.com/product/microsoft-teams-room-system-mvc800II) |Core i5|8 GB | 128 GB|
  |[Yealink MVC 900 II](https://www.yealink.com/product/microsoft-teams-room-system-mvc900II) |Core i5|8 GB | 128 GB|
  |[Yealink MVC840](https://www.yealink.com/product/microsoft-teams-room-system-mvc840) |Core i5|8 GB | 128 GB|
  |[Yealink MVC940](https://www.yealink.com/product/microsoft-teams-room-system-mvc940) |Core i5|8 GB | 128 GB|
  |Yealink MVC660|Core i5|8 GB | 128 GB|
  |Yealink MVC640|Core i5|8 GB | 128 GB|
  |Yealink MVC320|Core i5|8 GB | 128 GB|
  |Yealink MVC340|Core i5|8 GB | 128 GB|
  
  
> [!NOTE]
> - 不支援 Core M3 處理器。
> - 您需要設為 Windows 10 企業版可開機 Windows 安裝媒體的 32 GB 或更大型 USB 磁碟機。

**支援用於擴充座式系統的 Surface Pro 平板電腦**

  |平板電腦|處理器|RAM|磁碟|
  |:-----|:-----|:-----|:-----|
  |Surface Pro 6| Core i5 |16 GB 或 8 GB |128 GB 或更多 |
  |Surface Pro </br>(第五代) |Core i5 |8 GB 或 4 GB |128 GB 或更多 |
  |Surface Pro 4 |Core i5 |8 GB 或 4 GB |128 GB 或更多 |

- Surface Pro裝置需要下列其中一個連接基座選項：

  - [Logitech SmartDock](https://www.logitech.com/product/smartdock)
  - [Crestron SR](https://www.crestron.com/products/line/sr-for-skype-for-business-room-system )
  - [Polycom MSR Series](https://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.html)

### <a name="certified-firmware-versions-for-usb-audio-and-video-peripherals"></a>USB 音訊和視訊週邊設備的認證韌體版本

這些裝置可在[會議室系統配件產品展示](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73&page=1&filterIds=)和 [https://office.com/teamsdevices](https://office.com/teamsdevices) 中取得。

|Microsoft Teams 會議室週邊設備|認證的韌體版本 | 相機支援內容相機使用|
|:--- |:--- | :--- |
|[Aver VC520 Pro 相機 + 免持聽筒](https://www.averusa.com/products/conference-camera/vc520pro) |1004.35|
|[Aver VC520 PRO2 會議系統](https://www.averusa.com/products/conference-camera/vc520pro2) | 00.0.7200.79 |
|[Aver VB342+ 相機聲列](https://www.averusa.com/products/conference-camera/vb342plus) | 音效列：0.0.0000.97|
|[Aver CAM 540](https://www.averusa.com/products/conference-camera/cam540) |0.0.6002.83 |
|[Aver CAM 520 Pro](https://www.averusa.com/products/conference-camera/cam520pro) |0.0.1000.73 |
|[Aver CAM 520 Pro 2](https://www.averusa.com/products/conference-camera/cam520pro2) |0.0.7200.3 |
|[Aver CAM 130](https://www.averusa.com/products/conference-camera/cam130) |0.0.7450.02 | &#x2714; |
|[Aver VB130 相機聲列](https://www.averusa.com/products/conference-camera/vb130) |0.0.7300.71 |
|[Bose 視訊列 VB1](https://pro.bose.com/en_us/products/conferencing/videobars/bose-videobar-vb1.html?mc=25_PS_VB_BO_00_BI_&&msclkid=fc99b79880f714727a63e86ea0e5642a&utm_source=bing&utm_medium=cpc&utm_campaign=US%20-%20Brand_Videobar%20VB1_Exact&utm_term=bose%20videobar%20vb1&utm_content=Bose%20Videobar%20VB1&gclid=fc99b79880f714727a63e86ea0e5642a&gclsrc=3p.ds) |19.2|
|[Biamp Devio SCR-20CX Web-Based具有 Ceiling Microphone 的會議中心](https://www.biamp.com/products/product-families/devio/huddle-room-solutions) |2.2.0.9|
|[使用桌面麥克風的 Biamp Devio SCR-20TX Web-Based會議中心](https://www.biamp.com/products/product-families/devio/huddle-room-solutions) |2.2.0.9 |
|[Crestron Huddly IQ](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Accessories/CCS-CAM-USB-F-400)   | 1.02.09.33901  | 
|[哈茲利畫布](https://www.huddly.com/blog/say-hello-to-huddly-canvas-our-latest-ai-technology-for-content-capture-and-enhancement/) | 1.3.25 |  &#x2714; |
|[Huddly IQ](https://www.huddly.com/conference-cameras/iq/) |1.3.22|
|[Huddly IQ Lite](https://www.huddly.com/conference-cameras/iq/) |1.3.29|
|[Huddly IQ 相機](https://www.huddly.com/conference-cameras/iq/) |1.3.27|
|[Huddly L1](https://www.huddly.com/conference-cameras/l1/) | 1.2.9 |
|Huddly L1 相機與[Cres 要點 UC-C100-T MTR](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C100-T)套件 | Huddly L1 相機：1.2.1 </br> Cres 要 UC-C100-T 搭配 ASUS Tek Computer INC 9934 計算 1.0.20.246 或更新版本 |
|Huddly L1 相機與[Cresenovo UC-CX100-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-CX100-T) MTR-W Kit | Huddly L1 相機：1.2.9 </br> Cres}UC-CX100-T 搭載 ASUS Tek Computer INC 9934 1.00.20.246 或更新版本 |
|含 Cresenovo UC-M70-T MTR 套件的 Huddly L1 相機 | Huddly L1 相機：1.2.1 </br> Cres tenant UC-M70-T with ASUS Tek Computer INC 9934 compute 1.0.20.246 或更新版本 |
|Huddly L1 相機含 Cres 括弧 UC-MX70-T MTR 套件 | Huddly L1 相機：1.2.1 </br> Cres tenant UC-MX70-T with ASUS Tek Computer INC 9934 compute 1.0.20.246 或更新版本 |
|[Jabra Panacast3 相機](https://www.jabra.com/business/video-conferencing/jabra-panacast)|1.3.9.12|
|[Jabra Panacast 50 視訊列](https://www.jabra.com/business/video-conferencing/jabra-panacast-50)|3.4.0| &#x2714; |
|[Lenovo ThinkSmart Cam 相機](https://www.lenovo.com/us/en/accessories-and-monitors/webcams-and-video/webcams/SMARTOF-BO-ThinkSmart-Cam/p/4Y71C41660)|1.0.111.4|
|[Lenovo ThinkSmart Bar](https://www.lenovo.com/us/en/virtual-reality-and-smart-devices/smart-collaboration/thinksmart/ThinkSmart-Bar/p/11SP1TSSDBR)|0.9.3|
|Lenovo ThinkSmart Bar Expand XL|5.9.5|
|[Logitech Brio](https://www.logitech.com/product/brio)   |V2.2.50| &#x2714; |
|[Logitech 930e](https://www.logitech.com/product/c930e-webcam)   | 8.0.914   | &#x2714; |
|[Logitech Rally](https://www.logitech.com/product/rally-ultra-hd-conferencecam)   |1.2.4 |
|[Logitech 方塊](https://www.logitech.com/products/video-conferencing/room-solutions/rallybar.960-001308.html)   |10.3.82|
|[Logitech 欄 Mini](https://www.logitech.com/en-us/products/video-conferencing/room-solutions/rallybarmini.960-001336.html) |10.5.880|
|[Logitech MeetUp](https://www.logitech.com/product/meetup-conferencecam)   |音訊 - 1.0.172 <br/> 視訊 - 1.0.156  |
|[Logitech ConferenceCam Connect](https://www.logitech.com/product/conferencecam-connect)   |1.1.248.0 <br/> 1.1.684   |
|[Logitech Group](https://www.logitech.com/product/conferencecam-group)   |8.5.778   |
|[Logitech PTZ Pro](https://www.logitech.com/product/conferencecam-ptz-pro)   | 1.1.219   |
|[Logitech PTZ Pro 2](https://www.logitech.com/product/conferencecam-ptz-pro2)   |
|[Logitech Scribe](https://www.logitech.com/en-us/products/video-conferencing/room-solutions/scribe.960-001332.html) | 1.1.1 | &#x2714; |
|[Nureva HDL300](https://www.nureva.com/audio-conferencing/hdl300) |2.3.6|
|[Poly Eagle Eye Cube Camera](https://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.html)  |1.2.0 |
|[Polycom EagleEye IV](https://www.poly.com/us/en/products/video-conferencing/eagleeye/eagleeye-iv)   |1.0.0   |
|[Polycom CX5100](https://www.polycom.com/products-services/products-for-microsoft/lync-optimized/cx5100-unified-conference-station.mdl)   | 1.2.0.70232   |
|[Polycom Eagle Eye Director II](https://www.polycom.com/hd-video-conferencing/peripherals/eagleeye-director-ii.html)|2.1.0.10|
|[Polycom Studio Soundbar](https://www.polycom.com/hd-video-conferencing/room-video-systems/polycom-studio.html)|1.1.2.000570|
|[Poly Sync 40](https://www.poly.com/us/en/products/phones/sync/sync-40)|0.0.94.1461|
|[Poly Sync 60](https://www.poly.com/us/en/products/phones/sync/sync-60)|0.0.150.1671|
|[Polycom Trio 8500 / 8800](https://www.polycom.com/voice-conferencing-solutions/conference-phones/trio.html)   |5.7.2.3205|
|[Poly Trio C60](https://www.poly.com/us/en/products/phones/trio/trio-c60)  |5.9.5.3066|
|[Poly Studio P15 視訊列](https://www.poly.com/us/en/products/video-conferencing/studio-p/studio-p15)|1.2.0.000287 |
|[Poly Studio E70 相機](https://www.poly.com/us/en/products/video-conferencing/studio/studio-e70)|1.1|
|[EPOS SP 220 MS](http://no-no.sennheiser.com/dual-speakerphones-sp-220-ms-uc)   |2.0.12.0   |
|[EPOS SP20](https://www.eposaudio.com/en/us/enterprise/products/sp-20-ml-142ee5ca-speakerphone-1000226)   |1.2.15   |
|[EPOS SP30](https://www.eposaudio.com/en/us/enterprise/products/sp-30-78c0cecc-bluetooth-speakerphone-1000223)   |2.1.52  |
|[EPOS SP30T](https://www.eposaudio.com/en/us/enterprise/products/sp-30t-b949fe9a-bluetooth-speakerphone-1000225)  |3.2.63  |
|[EPOS Expand 80T + 2 擴充功能麥克風](https://www.eposaudio.com/en/us/enterprise/products/expand-80t-bluetooth-speakerphone-1000203) |免持聽筒 - 4.6.55 <br/> 擴充麥克風 - 0.2.314|
|[EPOS Expand Capture 5](https://www.eposaudio.com/en/us/enterprise/products/expand-capture-5-speakerphone-1000895)  |1.0.1|
|[Ex字元 DMP128 PLUS C V AT DSP System (DMP 128 Plus C V AT， DMP 128 Plus C AT， DMP 128 Plus C V， DMP 128 Plus C， DMP 128 Plus AT， DMP 128 Plus， DMP 128LexPlus C AT， DMP 128LexPlus C AT) ](https://www.extron.com/product/dmp128plus) | 1.08 |
|[Ex字元 DMP 64 PLUS C V AT DSP System (DMP 64 Plus C V AT， DMP 64 Plus C AT， DMP 64 Plus C V， DMP 64 Plus C) ](https://www.extron.com/product/dmp64plus) | 1.08|
|[Jabra 510](http://www.jabra.com/support/Jabra-SPEAK&trade;-510_7510-209)   |2.10.0   |
|[Jabra 710](http://www.jabra.com/business/speakerphones/jabra-speak-series/jabra-speak-710)   |1.8.0   |
|[Jabra 810](http://www.jabra.com/supportpages/jabra-speak-810)   |1.2.23   |
|[Yamaha YVC-1000](http://www.yamaha.com/products/en/communication/usb_conference_speakerphones/yvc-1000/)   |100c   |
|[Yamaha YVC-1000MS](https://uc.yamaha.com/products/conference-phones/usb-bluetooth/) |1.0.0 |
|[雅瑪 ADECIA Ceiling Solution](https://uc.yamaha.com/products/microphone-systems/adecia/)|1.2.0|
|[Yamaha ADECIA 平板解決方案](https://uc.yamaha.com/products/adecia/adecia-tabletop/)|表格麥克風的 E1.2.0，處理器的 D1.2.0 (兩者的內容與 V1.5.1) |
|[Yealink CP900](https://www.yealink.com/products_150.html) |100.20.0.29 |
|[Yealink UVC30](https://www.yealink.com/product/microsoft-teams-room-system-uvc30)| 105.420.0.11 |  &#x2714; |
|[Yealink UVC34 一體式視訊列](https://www.yealink.com/product/usb-videobar-uvc34) | 265.410.0.9 |
|[Yealink UVC40 一體式視訊列](https://www.yealink.com/product/usb-videobar-uvc40) |128.410.0.10|  
|[Yealink UVC84](https://www.yealink.com/product/camera-uvc84) |262.410.0.10|
|[Yealink UVC86]( https://www.yealink.com/product/camera-uvc86) |151.410.0.5|
|[Shure Intellimix P300 Audio Conferencing Processor](https://www.shure.com/products/mixers/p300)+</br>[Shure MXA 310 Table Array Mic ](https://www.shure.com/products/microphones/mxa310) | 4.1 |
|[Shure Intellimix P300 Audio Conferencing Processor](https://www.shure.com/products/mixers/p300) +</br>[Shure MXA 910 with Intellimix Ceiling Array Mic](https://www.shure.com/products/microphones/mxa910) | 4.1|
|[Shure Intellimix P300 Audio Conferencing Processor](https://www.shure.com/products/mixers/p300)+</br>[Shure MXA 310 Table Array Mic ](https://www.shure.com/products/microphones/mxa310) +</br>[MXN5W-C Ceiling 喇叭](https://www.shure.com/en-US/products/loudspeakers/mxn5)| P300 DSP：4.1.11 </br> MXA310 表格陣列麥克風：4.1.41 </br> MXN5W-C 喇叭：1.0.4 |
|[Shure Intellimix P300 Audio Conferencing Processor](https://www.shure.com/products/mixers/p300) + </br>[Shure MXA 910 搭載 Intellimix Ceiling Array Mic](https://www.shure.com/products/microphones/mxa910) +</br>[MXN5W-C Ceiling 喇叭](https://www.shure.com/en-US/products/loudspeakers/mxn5)| P300 DSP：4.1.11 </br> MXA910 Ceiling Array mic： 4.1.41 </br> MXN5W-C 喇叭：1.0.4 |
|[Shure MXA 710 2ft Table 線性陣列麥克風](https://www.shure.com/products/microphones/mxa710) + </br>[Shure Intellimix P300 Audio Conferencing Processor](https://www.shure.com/products/mixers/p300) +</br>[MXN5-C Ceiling Speaker](https://www.shure.com/en-US/products/loudspeakers/mxn5)| MXA710 2ft Table 線性陣列麥克風：1.2.0 </br> P300 DSP：4.4.8 </br> MXN5-C 喇叭：1.1.1 |
|[Shure MXA 710 4ft Wall 線性陣列麥克風](https://www.shure.com/products/microphones/mxa710) + </br>[Shure Intellimix P300 Audio Conferencing Processor](https://www.shure.com/products/mixers/p300) +</br>[MXN5-C Ceiling Speaker](https://www.shure.com/en-US/products/loudspeakers/mxn5)| MXA710 4ft Wall 線性陣列麥克風：1.2.0 </br> P300 DSP：4.4.8 </br> MXN5-C 喇叭：1.1.1 |
|[Shure MXA 910 搭配 Intellimix Ceiling Array Microphone](https://www.shure.com/products/microphones/mxa910) + </br> [Shure Intellimix Room Software](https://www.shure.com/products/software/intellimix_room) +</br> [Cres}UC-C100-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C100-T)| Shure Intellimix Room Software： 3.0.4.14 </br> Shure MXA 910 with Intellimix Ceiling Array Microphone： 4.4.11 </br> Shure MXN5-C 喇叭：1.2.1 </br> Cres 要 UC-C100-T 搭配 ASUS Tek Computer INC 9934 計算 | 
|[Shure MXA 910 搭配 Intellimix Ceiling Array Microphone](https://www.shure.com/products/microphones/mxa910) + </br> [Shure Intellimix Room Software](https://www.shure.com/products/software/intellimix_room) +</br>Lenovo ThinkSmart Core | Shure Intellimix Room Software： 3.2.0.52 </br> Shure MXA 910 with Intellimix Ceiling Array Microphone： 4.4.11 </br> Shure MXN5-C 喇叭：1.2.1 </br> Lenovo ThinkSmart Core：Windows IoT 19h2/20h2 OS 版本 |
|[Sennheiser TeamConnect 智慧型喇叭/TC ISP (T-Rock) ](https://en-us.sennheiser.com/tcisp)|1.0.2|
|[Biamp Tesira Fore AVB VT4 Fixed audio DSP](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ &Dagger;</br>[Sennheiser TeamConnect Ceiling 2 Microphone](https://sennheiser.com/tcc2)+ &Dagger;</br>[Tesira EX-UBT](https://www.biamp.com/products/tesira/tesira-expanders) &Dagger; |  Biamp DSP：3.12.0.15 </br> TCC2：1.3.3 </br>EX-UBT：3.12.0.15 |
|[Biamp Tesira FORTÉ AVB VT4 Audio DSP](https://www.biamp.com/products/tesira-fixed-audio-dsp)+</br>[Biamp Parlé TCM-XA Ceiling 麥克風](https://www.biamp.com/products/product-families/parle/parle-microphones)+</br>[Biamp Desono C-IC6 ceiling mounted loudspeaker](https://www.biamp.com/products/tesira-speakers)| 音訊 FW 版本：3.15|
|[Biamp TesiraFORTE AVB VT4](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ </br>[Parle TTM-X (Table Mic) ](https://www.biamp.com/products/product-families/parle/parle-microphones)+</br>[Ex-UBT]() |音訊 FW 版本：3.15|
|Biamp Tesira FORTE X Series +</br>[Devio SCX Series](https://www.biamp.com/products/product-families/devio/medium-large-room-solutions#devio-scx-400)|Tesira FORTE X Series： 4.2.5 </br> Devio SCX 系列：4.2.5|
|[Bose ControlSpace EX-440C DSP + </br>Bose P2600A AmpLink Amplifier +</br> Sennheiser TCC2 Ceiling Microphone + </br> Bose EdgeMax EM180 Ceiling Speaker](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html)|  Bose DSP：2.290  </br> P2600A：1.160  </br> TCC2：1.4.2  |  |
|[Bose ControlSpace EX-440C DSP + </br> Bose P2600A AmpLink Amplifier + Sennheiser TCC2 Ceiling Microphone + </br> Bose DesignMax DM2C-P Ceiling Speaker](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html)|  Bose DSP：2.290  </br> P2600A：1.160  </br> TCC2：1.4.2  |  |
|[Bose ControlSpace EX-1280C DSP](https://pro.bose.com/en_us/products/signal_processing_and_networking/controlspace_ex/cs_ex_1280c.html#v=cs_ex_1280c_black) +</br>Bose P2600A AmpLink Amplifier +</br> [Sennheiser TCC2 Ceiling Microphone](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html) +</br> [DesignMax DM2C -LP Ceiling Speaker](https://pro.bose.com/en_us/products/loudspeakers/background_foreground/designmax/designmax_dm2c_lp.html#v=designmax_dm2c_lp_black) | Bose DSP：2.290  </br> P2600A：1.160  </br> TCC2：1.4.2  | 
|[Bose ControlSpace EX-1280C DSP](https://pro.bose.com/en_us/products/signal_processing_and_networking/controlspace_ex/cs_ex_1280c.html#v=cs_ex_1280c_black) +</br>Bose P2600A AmpLink Amplifier+</br> [Sennheiser TCC2 Ceiling Microphone](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html) +</br> [EdgeMax EM180 Ceiling Speaker](https://pro.bose.com/en_us/products/loudspeakers/background_foreground/edgemax/edgemax_em180.html#v=edgemax_em180_white) | Bose DSP：2.290  </br> P2600A：1.160  </br> TCC2：1.4.2  |
|QSC Q-SYS Core ([110f](https://www.qsc.com/solutions-products/q-sys-ecosystem/processing/core-110f/)、 [8Lex](https://www.qsc.com/solutions-products/q-sys-ecosystem/processing/core-8-flex/)、 [Nano](https://www.qsc.com/solutions-products/q-sys-ecosystem/processing/core-nano/)或 [NV-32-H](https://www.qsc.com/solutions-products/q-sys-ecosystem/processing/nv-32-h-core-capable/)) + </br> [Sennheiser TCC2 Ceiling Microphone](https://en-us.sennheiser.com/tcc2) + </br> QSC Amplifier ([SPA 系列](https://www.qsc.com/solutions-products/power-amplifiers/installed/non-network/low-power-applications/spa-series/) 或 [CX-Q 系列](https://www.qsc.com/solutions-products/power-amplifiers/installed/network/cx-q-series/)) + </br> [QSC AcousticDesign Series 喇叭](https://www.qsc.com/solutions-products/loudspeakers/installed/passive/solutions/acousticdesigntm-series-solutions/) + </br> QSC IP 相機 ([PTZ-IP 20x60](https://www.qsc.com/solutions-products/q-sys-ecosystem/video/ptz-ip-conference-cameras/)、[PTZ-IP 12x72](https://www.qsc.com/solutions-products/q-sys-ecosystem/video/ptz-ip-conference-cameras/)) 選用 + </br> [QSC Q-SYS I/O USB Bridge](https://www.qsc.com/solutions-products/q-sys-ecosystem/audio-io-peripherals/io-usb-bridge/) 選用 | QSC Q-SYS Core、PTZ-IP 相機 和 I/O USB 橋接器：QSC Q-SYS Designer 9.0.1-2104.022 </br> Sennheiser TCC2 Ceiling Microphone：TCC2 - 1.5.1、Dante 1.2.0 </br> QSC 擴充程式：不適用 </br> QSC AcousticDesign Series Loudspeakers： N/A | 


&Dagger; 客戶可以選擇 Dante 介面或 Biamp/Sennheiser 針對此套件建議的網路交換器。

#### <a name="usb-extenders"></a>USB 延伸器

- 平板電腦擴充座上的 USB 連接埠與 USB 3.0 相容。 您可以使用 USB 2.x 延伸器，但最遠端只能使用 USB 2.x 速度。 不建議對 USB 3.0 週邊設備使用延伸器。
- 延伸器必須符合 USB 2.0 或更新規格。
  - 平板電腦擴充座支援至少兩段外部 USB 集線器延長線。 如果您以序列連接兩個以上的 USB 集線器，請洽詢擴充座製造商，確認是否支援系列連接。
  - 會議室中具備有線 GbE 連線。 長度適當的乙太網路纜線。
  - 最多兩個具有 HDMI 連線的 1080p 顯示器。 長度適當的 HDMI 纜線。

> [!NOTE]
> 在作為會議室前方顯示器的消費者電視，必須支援/啟用 HDMI 的消費者電子控制 (CEC) 功能，使得它能夠自動從待機模式切換為使用中的視訊來源。 此功能在所有電視上均不支援。
>
> Microsoft Teams 會議室不使用鍵盤。 如有需要，系統管理員應使用螢幕小鍵盤。 處理 Microsoft Teams 會議室裝置影像時，會需要 USB 鍵盤或滑鼠。

下表根據會議室規模提供週邊設備建議：

**Microsoft Teams 會議室認證音訊週邊設備**

|會議室類型|人數|麥克風與喇叭之間建議的最大距離|
|:-----|:-----|:-----|
|**焦點** <br/> 10' x 9'   |2-4  |1.5 m  |
|**小型** <br/> 16' x 16'  |4-6  |2.0 m  |
|**中型** <br/> 18' x 20'  |6-12  |2.4 m  |
|**大型** <br/> 15' x 32'  |12-16  |3 m <br/> 此距離也適用每個連接衛星式麥克風所涵蓋的區域。  |

**Microsoft Teams 會議室認證視訊週邊設備**

|會議室類型|人數|
|:-----|:-----|
|**焦點** <br/> 10' x 9'  |2-4  |
|**小型** <br/> 16' x 16'  |4-6  |
|**中型** <br/> 18' x 20'  |6-12  |
|**大型** <br/> 15' x 32'  |12-16  |

 > [!NOTE]
 > 會議室前方顯示器解析度應設定為不大於 1920x1080p。


## <a name="see-also"></a>另請參閱

[瀏覽所有套件組合](https://products.office.com/microsoft-teams/across-devices/devices)

[規劃 Microsoft Teams 會議室](rooms-plan.md)

[部署 Microsoft Teams 會議室](rooms-deploy.md)

[設定 Microsoft Teams 會議室主控台](console.md)

[管理 Microsoft Teams 會議室](rooms-manage.md)
