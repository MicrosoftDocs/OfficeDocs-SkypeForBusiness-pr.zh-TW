---
title: Microsoft 團隊會議室需求
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
ms.assetid: 6b2b2684-8e9e-49ea-8c46-1c690964f982
ms.collection:
- M365-collaboration
description: 本文將摘要說明支援 Microsoft 團隊聊天室的需求。
ms.openlocfilehash: 9e0aa01e72fee194dc57af733adfdfa59e6fce71
ms.sourcegitcommit: 361ca60a66bab31cd54d8c1f805697460427e44d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/18/2019
ms.locfileid: "38696813"
---
# <a name="microsoft-teams-rooms-requirements"></a>Microsoft 團隊會議室需求

Microsoft 團隊聊天室會根據房間大小及用途，使用各種經認證的音訊和視頻週邊數來調整不同的房間大小。 您可以選取適當的核心裝置和主控台（結合麥克風、喇叭、相機，並針對空間顯示），將 Microsoft 團隊會議室從非常小的 huddle 空間部署到大量的會議空間然後 boardrooms。  [裝置展示](https://products.office.com/microsoft-teams/across-devices)中提供了所有可用來設定您房間的已鑒定音訊及視頻外設的完整集合。

本文摘要說明支援 Microsoft 團隊聊天室的裝置部署與設定需求。

您的部署涉及帳戶建立，如[部署 Microsoft 團隊聊天室](room-systems-v2.md)及設定會議主控台中所述，請參閱設定[microsoft 團隊聊天室主控台](console.md)中所述。

另請參閱：

- [商務用 Skype 附加元件授權](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)
- [以您的方案為基礎的授權選項： Microsoft 球隊會議室](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2)

> [!NOTE]
> Microsoft 球隊會議室登入 Microsoft 團隊、商務用 Skype Server 2019、商務用 skype Server 2015 或商務用 Skype Online，並可能加入由這些服務託管的會議。
>
> Microsoft 團隊聊天室不支援舊版平臺（例如 Lync Server 2013）。 在由世紀運營的 Office 365 或 GCC-高或 DoD 的環境中，Microsoft 球隊會議室不受支援。
>
> 如果您有內部部署 Exchange 伺服器，Microsoft 團隊聊天室需要使用 Exchange Server 2013 SP1 或更新版本。

## <a name="hardware-requirements"></a>硬體需求
硬體部署包括 Microsoft 團隊房間系統的選取範圍，與已驗證的音訊和視頻外設結合，以及將這些裝置整合在一起的纜線方案。  這些選項將在這裡說明。

**支援的 Microsoft 團隊房間系統**

在[房間系統產品展示](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=20&page=1&filterIds=)中，所有目前的 Microsoft 團隊聊天室裝置和套件都可使用。

  |控制|處理器類型|RAM|光碟|
  |:-----|:-----|:-----|:-----|
  |[Crestron Flex UC-M130-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M130-T)|核心 i5|8 GB |128 GB |
  |[Crestron Flex UC-B130-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B130-T)|核心 i5|8 GB |128 GB |
  |[Crestron Flex UC-B140-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B140-T)|核心 i5|8 GB |128 GB |
  |[Crestron Flex UC-M150-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M150-T)|酷睿 i7|8 GB |128 GB |
  [Crestron Flex UC-B160-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B160-T)|酷睿 i7|8 GB |128 GB|
  |[Crestron Flex UC-C160-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C160-T)|酷睿 i7|8 GB|128 GB|
  |[[會議室] G2 的 [HP 精英] 扇面](https://www8.hp.com/us/en/elite-family/elite-slice-for-meetings.html) |核心 i5 |8 GB |128 GB |
  |[HP 精英扇面中的 [Microsoft 團隊會議室] 可準備好音訊](https://store.hp.com/us/en/pdp/hp-elite-slice-for-meeting-rooms-g2-skype-room-systems-audio-ready?jumpid=cp_r12131_us/en/psg/elite_slice_for_meetings/product/shop-now-eliteslicemeeting-g2-audio) |核心 i5 |8 GB |128 GB |
  |[聯想 ThinkSmart 中樞500](https://www3.lenovo.com/us/en/hub500) |核心 i5 |8 GB |128 GB |
  |[Logitech 攻絲](https://www.logitech.com/product/microsoft-rooms)|核心 i5|8 GB |128 GB |
  |[Yealink MVC800](https://www.yealink.com/products_125.html)|核心 i5|8 GB|128 GB|
  |[Yealink MVC500](https://www.yealink.com/products_126.html)|核心 i5|8 GB |128 GB |
  |[Yealink MVC300](https://www.yealink.com/products_154.html)|核心 i5|8 GB |128 GB |
  ||||||

> [!NOTE]
> - 不支援核心 M3 處理器。
> - 您需要將 32 GB 或更大的 USB 磁片磁碟機設定為 Windows 10 企業版的可引導 Windows 安裝媒體。

**支援用於 dock 樣式系統的 Surface Pro 平板電腦**

  |平板電腦|處理器類型|RAM|光碟|
  |:-----|:-----|:-----|:-----|
  |Surface Pro 6| 核心 i5 |16 GB 或 8 GB |128 GB 以上 |
  |Surface Pro </br>（第5代） |核心 i5 |8 GB 或 4 GB |128 GB 以上 |
  |Surface Pro 4 |核心 i5 |8 GB 或 4 GB |128 GB 以上 |

- 下列其中一個對接站選項，可將平板電腦固定在會議室表格。

  - [Logitech SmartDock](https://www.logitech.com/product/smartdock)
  - [Crestron SR](http://www.crestron.com/products/line/sr-for-skype-for-business-room-system )
  - [Polycom MSR 系列](http://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.html)

### <a name="certified-firmware-versions-for-usb-audio-and-video-peripherals"></a>USB 音訊與視頻週邊設備的認證固件版本

這些裝置可在[房間系統附件產品展示](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73&page=1&filterIds=)及[https://office.com/teamsdevices](https://office.com/teamsdevices)中取得。

|Microsoft 團隊聊天室週邊|認證的固件版本 | 相機支援內容相機使用|
|:--- |:--- | :--- |
|[Crestron Huddly IQ](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Accessories/CCS-CAM-USB-F-400)   | 1.02.09.33901  | &#x2714; |
|[Logitech Brio](https://www.logitech.com/product/brio)   |V 2.2.50| &#x2714; |
|[Logitech 930e](http://www.logitech.com/product/c930e-webcam)   | 8.0.914   | &#x2714; |
|[Logitech Rally](https://www.logitech.com/product/rally-ultra-hd-conferencecam)   |1.2.4 |
|[Logitech 頻道](http://www.logitech.com/product/meetup-conferencecam)   |音訊-1.0.172 <br/> 影片-1.0.156  |
|[Logitech ConferenceCam Connect](http://www.logitech.com/product/conferencecam-connect)   |1.1.248.0 <br/> 1.1.684   |
|[Logitech 群組](http://www.logitech.com/product/conferencecam-group)   |8.5.778   |
|[Logitech PTZ Pro](http://www.logitech.com/product/conferencecam-ptz-pro)   | 1.1.219   |
|[Logitech PTZ Pro 2](http://www.logitech.com/product/conferencecam-ptz-pro2)   |
|[Polycom EagleEye IV](http://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.mdl)   |1.0.0   |
|[Polycom CX5100](http://www.polycom.com/products-services/products-for-microsoft/lync-optimized/cx5100-unified-conference-station.mdl)   | 1.2.0.70232   |
|[Polycom Eagle 目主管 II](https://www.polycom.com/hd-video-conferencing/peripherals/eagleeye-director-ii.html)|2.1.0.10|
|[Polycom Studio Soundbar](https://www.polycom.com/hd-video-conferencing/room-video-systems/polycom-studio.html)|1.1.2.000570|
|[Polycom 組 8500/8800](https://www.polycom.com/voice-conferencing-solutions/conference-phones/trio.html)   |5.7.2.3205|
|[Sennheiser SP 220 MS](http://no-no.sennheiser.com/dual-speakerphones-sp-220-ms-uc)   |2.0.12.0   |
|[Sennheiser SP20](http://en-us.sennheiser.com/sp-20-og-sp-20-ml)   |1.2.15   |
|[Sennheiser SP30](https://en-us.sennheiser.com/sp-30)   |2.1.52  |
|[Jabra 510](http://www.jabra.com/support/Jabra-SPEAK™-510_7510-209)   |2.10.0   |
|[Jabra 710](http://www.jabra.com/business/speakerphones/jabra-speak-series/jabra-speak-710)   |1.8.0   |
|[Jabra 810](http://www.jabra.com/supportpages/jabra-speak-810)   |1.2.23   |
|[Yamaha YVC-1000](http://www.yamaha.com/products/en/communication/usb_conference_speakerphones/yvc-1000/)   |100c   |
|[Yealink CP900](https://www.yealink.com/products_150.html) | 100.20.0.29|  
|[Biamp Tesira AVB VT4 Fixed audio DSP](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ &Dagger;</br></br> [Sennheiser TeamConnect 天花板2麥克風](https://en-us.sennheiser.com/tcc2)+ &Dagger;</br></br> [TESIRA EX-UBT](https://www.biamp.com/products/tesira/tesira-expanders)&Dagger; |  Biamp DSP：3.12.0.15  </br></br> TCC2: 1.3.3 </br></br> EX-UBT：3.12.0.15 |  |
||||||

&Dagger;客戶可以選擇 Biamp/Sennheiser 針對這種套件所建議的 Dante 介面或網路交換器。

#### <a name="usb-extenders"></a>USB 延伸器

- 平板電腦上的 USB 埠會相容 USB 3.0。 您可以使用 USB 2. x 延伸器，但這樣做會限制您在最一端的 USB 2. x 速度。 對於 USB 3.0 外設，不建議使用延伸程式。
- 擴展程式必須符合 USB 2.0 或更新的規格。
  - 平板電腦停靠支援至少兩個外部 USB 中樞延伸的階段。 如果您在數列中連接兩個以上的 USB 集線器，請向 dock 製造商確認其是否支援串聯介面。
  - 會議室中的有線 GbE 連接。 適當長度的乙太網纜線。
  - 最多 2 1080-p 顯示器與 HDMI 連線。 適當長度的 HDMI 纜線。

> [!NOTE]
> 用來做為會議室顯示的消費者電視需要支援/啟用 HDMI 的消費電子產品控制（CEC）功能，讓它能從待機模式自動切換到作用中的影片來源。 並非所有電視都支援這項功能。
>
> Microsoft 團隊會議室不使用鍵盤。 如有需要，系統管理員應該使用螢幕小鍵盤。 當您將 Microsoft 團隊聊天室裝置進行影像處理時，將需要 USB 鍵盤或滑鼠。

下表根據房間大小提供針對週邊設備的建議：

**Microsoft 團隊聊天室認證的音訊外設**

|會議室類型|人數|建議從麥克風到喇叭的最大距離|裝置（依最大房間大小）|批註|
|:-----|:-----|:-----|:-----|:-----|
|**處理** <br/> 10 "x 9"   |2–4  |1.5 m  |Logitech Connect  |Logitech [連接裝置] 包含的相機必須位於房間的前方（不是表格中央），才能捕獲當地會議出席者。 |
|**小規模** <br/> 16 "x 16"  |4至6  |2.0 m  |Jabra 510 <br/> Sennheiser SP20  |播放音量限制在較大的房間中。  |
|**深淺** <br/> 18 "x 20"  |6到12  |2.4 m  |Jabra 710 <br/> Jabra 810 <br/> Logitech 頻道 <br/> Logitech 群組 <br/> Polycom 組 <br/> Polycom CX5100 <br/> Sennheiser SP 220 MS <br/> Yamaha YVC-1000MS  |Logitech 頻道包含相機，所以它必須放在會議室正面（不是表格中央即可捕獲當地會議出席者）。 <br/> 一般來說，具有長矩形或 u 狀表格的房間，可能會從衛星麥克風獲益。 <br/> 您必須在菊輪鍊式配置中使用 SP 220 MS。  |
|**大中型** <br/> 15 "x 32"  |12–16  |3 m <br/> 這個距離也適用于每個連接的附屬麥克風所覆蓋的區域。  |Logitech 群組 + 附屬 mics <br/> Polycom 組 + 附屬 mics <br/> Polycom CX5100 + 附屬 mics <br/> Sennheiser SP 220 MS <br/> Yamaha YVC-1000MS + 衛星 mics  |此列中所列的所有音訊裝置都支援衛星麥克風選項。 <br/> CX5100 包含內建的360度相機，可將裝置放在表格的中央。 <br/> 您必須在菊輪鍊式配置中使用 SP 220 MS。  |

**Microsoft 團隊聊天室認證的視頻外設**

|會議室類型|人數|裝置（依最佳房間大小）|批註|
|:-----|:-----|:-----|:-----|
|**處理** <br/> 10 "x 9"  |2–4  |Logitech Connect <br/> Logitech 頻道 <br/> Polycom CX5100  ||
|**小規模** <br/> 16 "x 16"  |4至6  |Logitech C930e <br/> Logitech 頻道 <br/> Logitech BRIO <br/> Logitech PTZ Pro <br/> Polycom MSR <br/> Polycom CX5100  |Logitech PTZ Pro 通常與 Logitech 群組捆綁  |
|**深淺** <br/> 18 "x 20"  |6到12  |Logitech 頻道 <br/> Logitech BRIO <br/> Logitech PTZ Pro <br/> Polycom MSR <br/> Polycom CX5100  ||
|**大中型** <br/> 15 "x 32"  |12–16  |Logitech PTZ Pro <br/> Polycom MSR <br/> Polycom CX5100  ||

 > [!NOTE]
 > 房間顯示解析度的前面應該設定為 [不超過 1920x1080p]。

## <a name="required-software-downloads"></a>所需的軟體下載

若要建立您自己的 Microsoft 團隊聊天室圖像，請依照[設定 Microsoft 團隊聊天室主控台](console.md)中的指示進行。 這些指示會引導您下載安裝所需的所有軟體。

> [!NOTE]
> IT 專業人員必須透過大量授權協定，才能存取 Windows 10 企業版 ISO 檔案。

[SkypeRoomProvisioningScript](https://go.microsoft.com/fwlink/?linkid=870105)是可供您用來預配 Microsoft 團隊聊天室帳戶的選擇性下載。

## <a name="see-also"></a>另請參閱

[流覽所有捆綁包](https://products.office.com/microsoft-teams/across-devices/devices)

[規劃 Microsoft 團隊聊天室](skype-room-systems-v2-0.md)

[部署 Microsoft 團隊聊天室](room-systems-v2.md)

[設定 Microsoft 團隊聊天室主控台](console.md)

[管理 Microsoft 團隊聊天室](skype-room-systems-v2.md)

[商務用 Skype 附加元件授權](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)
