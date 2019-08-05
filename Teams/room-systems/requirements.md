---
title: Microsoft 團隊會議室需求
ms.author: v-lanac
author: lanachin
ms.reviewer: davgroom
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b2b2684-8e9e-49ea-8c46-1c690964f982
ms.collection: M365-voice
description: 本文將摘要說明支援 Microsoft 團隊聊天室的需求。
ms.openlocfilehash: 7e78c2f33a52d5848b8b996c65fefbeabdab4c3e
ms.sourcegitcommit: dcc5c09e6b891fe44c9d2cf384fe7ef678e7768c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/26/2019
ms.locfileid: "36185142"
---
# <a name="microsoft-teams-rooms-requirements"></a>Microsoft 團隊會議室需求

本文將摘要說明支援 Microsoft 團隊聊天室的需求。 

您的部署將涉及帳戶建立, 如[部署 Microsoft 團隊聊天室](room-systems-v2.md)中所述, 以及設定會議主控台, 如設定[microsoft 團隊聊天室主控台](console.md)中所述。 

您可能也需要參考:

- [商務用 Skype 附加元件授權](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)
- [以您的方案為基礎的授權選項: Microsoft 球隊會議室](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2)

> [!NOTE]
> Microsoft [團隊聊天室] 適用于 Microsoft 團隊、商務用 Skype Server 2019、商務用 Skype Server 2015 或商務用 Skype Online。 <br><br>較舊的平臺 (例如 Lync Server 2013) 不應與 Microsoft 團隊聊天室搭配使用。

> [!NOTE]
> 如果您使用的是內部部署 Exchange 伺服器, Microsoft 團隊聊天室需要使用 Exchange Server 2013 SP1 或更新版本。

## <a name="hardware-requirements"></a>硬體需求

Microsoft 球隊會議室可透過附件根據音訊和視頻週邊設備, 縮放至不同的房間大小。 本文中所列的硬體支援 Skype 與團隊會議模式。  音訊及視頻外設會透過塢站裝置上的 USB 或 HDMI 連接, 連線至 Microsoft 團隊聊天室。 您也需要:

- 您將32GB 或較大的 USB 磁片設定為 Windows 10 企業版的可引導 Windows 安裝媒體。 

- 下列平板電腦或主控台之一:

**支援的平板電腦**

|平板電腦|處理器類型|RAM|光碟|
|:-----|:-----|:-----|:-----|
|Surface Pro 6          |核心 i5  |不限或8GB |128GB 或更多  |
|Surface Pro (第5代)  |核心 i5  |8GB 或4GB  |128GB 或更多  |
|Surface Pro 4          |核心 i5  |8GB 或4GB  |128GB 或更多  |

- 下列其中一個對接站選項, 可將平板電腦固定在會議室表格。 

  - [Logitech SmartDock](https://www.logitech.com/product/smartdock)

  - [Crestron SR](http://www.crestron.com/products/line/sr-for-skype-for-business-room-system )

  - [Polycom MSR 系列](http://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.html)


**其他支援的 Microsoft 團隊聊天室主控台**

|控制|處理器類型|RAM|光碟|
|:-----|:-----|:-----|:-----|
|[Crestron Flex UC-M150-T](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M150-T)|酷睿 i7|GB |128GB |
[Crestron Flex UC-B160-T](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B160-T)|酷睿 i7|GB |128GB|
|[Crestron Flex UC-C160-T](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C160-T)|酷睿 i7|GB|128GB|
|[[會議室] G2 的 [HP 精英] 扇面](https://www8.hp.com/us/en/elite-family/elite-slice-for-meetings.html) |核心 i5  |GB  |128GB  | 
|[HP 精英扇面中的 [Microsoft 團隊會議室] 可準備好音訊](https://store.hp.com/us/en/pdp/hp-elite-slice-for-meeting-rooms-g2-skype-room-systems-audio-ready?jumpid=cp_r12131_us/en/psg/elite_slice_for_meetings/product/shop-now-eliteslicemeeting-g2-audio) |核心 i5 |GB |128GB | 
|[聯想 ThinkSmart 中樞500](https://www3.lenovo.com/us/en/hub500) |核心 i5  |GB  |128GB  |  
|[Logitech 攻絲](https://www.logitech.com/en-us/product/microsoft-rooms)|核心 i5|GB |128GB |
|[Yealink MVC800](https://www.yealink.com/products_125.html)|核心 i5|GB|128GB|
|[Yealink MVC500](https://www.yealink.com/products_126.html)|核心 i5|GB |128GB |
|||||

> [!NOTE]
> 不支援核心 M3 處理器。

**USB 音訊與視頻週邊設備的認證固件版本**

|Microsoft 團隊聊天室外設|針對 Microsoft 團隊聊天室認證的固件版本|
|:-----|:-----|
|[Logitech Rally](https://www.logitech.com/en-us/product/rally-ultra-hd-conferencecam) <br/> |1.2.4 |
|[Logitech BRIO](https://www.logitech.com/en-us/product/brio) <br/> |v240|
|[Logitech 頻道](http://www.logitech.com/en-us/product/meetup-conferencecam) <br/> |音訊-1.0.172  <br/> 影片-1.0.156  <br/> |
|[Logitech ConferenceCam Connect](http://www.logitech.com/en-us/product/conferencecam-connect) <br/> |1.1.248.0  <br/> 1.1.684  <br/> |
|[Logitech 群組](http://www.logitech.com/en-us/product/conferencecam-group) <br/> |8.5.778  <br/> |
|[Logitech 930e](http://www.logitech.com/en-us/product/c930e-webcam) <br/> | 8.0.914 <br/> |
|[Logitech PTZ Pro](http://www.logitech.com/en-us/product/conferencecam-ptz-pro) <br/> | 1.1.219 <br/> |
|[Logitech PTZ Pro 2](http://www.logitech.com/en-us/product/conferencecam-ptz-pro2) <br/> |
|[Polycom EagleEye IV](http://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.mdl) <br/> |1.0.0  <br/> |
|[Polycom CX5100](http://www.polycom.com/products-services/products-for-microsoft/lync-optimized/cx5100-unified-conference-station.mdl) <br/> | 1.2.0.70232 <br/> |
|[Polycom Eagle 目主管 II](https://www.polycom.com/hd-video-conferencing/peripherals/eagleeye-director-ii.html)|2.1.0.10|
|[Polycom 組 8500/8800](https://www.polycom.com/voice-conferencing-solutions/conference-phones/trio.html) <br/> |5.7.2.3205|
|[Sennheiser SP 220 MS](http://no-no.sennheiser.com/dual-speakerphones-sp-220-ms-uc) <br/> |2.0.12.0  <br/> |
|[Sennheiser SP20](http://en-us.sennheiser.com/sp-20-og-sp-20-ml) <br/> |1.2.15  <br/> |
|[Sennheiser SP30](https://en-us.sennheiser.com/sp-30) <br/> |2.1.52 <br/>|
|[Jabra 510](http://www.jabra.com/support/Jabra-SPEAK™-510_7510-209) <br/> |2.10.0  <br/> |
|[Jabra 710](http://www.jabra.com/business/speakerphones/jabra-speak-series/jabra-speak-710) <br/> |1.8.0  <br/> |
|[Jabra 810](http://www.jabra.com/supportpages/jabra-speak-810) <br/> |1.2.23  <br/> |
|[Yamaha YVC-1000](http://www.yamaha.com/products/en/communication/usb_conference_speakerphones/yvc-1000/) <br/> |100c  <br/> |

- **USB 延伸**程式:

  - 平板電腦上的 USB 埠會相容 USB 3.0。 您可以使用 USB x.x.x.x 擴展器, 但這樣做會將您限制在 USB 2 的速度, 而不建議 USB 3.0 外設執行此操作。

  - 擴展程式必須符合 USB 2.0 或更新的規格。

  - 平板電腦停靠支援至少兩個外部 USB 中樞延伸的階段。 如果需要連接數列中的兩個以上的 USB 中樞, 您必須向 dock 製造商核實, 以確認是否支援這項功能。

- 會議室中的有線 GbE 連接。 適當長度的乙太網纜線。

- 最多兩個1080p 顯示器, 並隨附 HDMI 連線。 適當長度的 HDMI 纜線。

> [!NOTE]
> 用來做為會議室顯示的消費者電視需要支援/啟用 HDMI 的消費電子產品控制 (CEC) 功能, 讓它能從待機模式自動切換到作用中的影片來源。 並非所有電視都支援這項功能。 

> [!NOTE]
> Microsoft 團隊會議室不使用鍵盤。 如有需要, 系統管理員應該使用螢幕小鍵盤。 當您將 Microsoft 團隊聊天室裝置進行影像處理時, 將需要 USB 鍵盤或滑鼠。 

下表根據房間大小提供針對週邊設備的建議:

**Microsoft 團隊聊天室認證的音訊外設**

|會議室類型|人數|建議從麥克風到說話的最大距離|裝置 (依最大房間大小)|批註|
|:-----|:-----|:-----|:-----|:-----|
|**處理** <br/> 10 "x 9"  <br/> |2-4  <br/> |1.5 m  <br/> |Logitech Connect  <br/> |Logitech 連接裝置包含相機, 所以它必須放在會議室的前方 (不是表格中央), 才能捕獲當地會議出席者。  <br/> |
|**小規模** <br/> 16 "x 16"  <br/> |4-6  <br/> |2.0 m  <br/> |Jabra 510  <br/> Sennheiser SP20  <br/> |播放音量可能受限於較大的會議室。  <br/> |
|**深淺** <br/> 18 "x 20"  <br/> |6-12  <br/> |2.4 m  <br/> |Jabra 710  <br/> Jabra 810  <br/> Logitech 頻道  <br/> Logitech 群組  <br/> Polycom 組  <br/> Polycom CX5100  <br/> Sennheiser SP 220 MS  <br/> Yamaha YVC-1000MS  <br/> |Logitech 頻道包含相機, 所以它必須放在會議室正面 (不是表格中央即可捕獲當地會議出席者)。  <br/> 一般來說, 具有長矩形或 u 狀表格的房間, 可能會受益于其他附屬麥克風。  <br/> 您必須在菊輪鍊式配置中使用 SP 220 MS。  <br/> |
|**大中型** <br/> 15 "x 32"  <br/> |12-16  <br/> |3m  <br/> 這個距離也適用于每個連接至有問題音訊裝置的其他附屬麥克風所覆蓋的區域。  <br/> |Logitech 群組 + 附屬 mics  <br/> Polycom 組 + 附屬 mics  <br/> Polycom CX5100 + 附屬 mics  <br/> Sennheiser SP 220 MS  <br/> Yamaha YVC-1000MS + 衛星 mics  <br/> |此列中所列的所有音訊裝置都支援衛星麥克風選項。  <br/> CX5100 包含內建的360度攝影機, 可將裝置放在表格的中央。  <br/> 您必須在菊輪鍊式配置中使用 SP 220 MS。  <br/> |

**Microsoft 團隊聊天室認證的視頻外設**

|會議室類型|人數|裝置 (依最佳房間大小)|批註|
|:-----|:-----|:-----|:-----|
|**處理** <br/> 10 "x 9"  <br/> |2-4  <br/> |Logitech Connect  <br/> Logitech 頻道  <br/> Polycom CX5100  <br/> ||
|**小規模** <br/> 16 "x 16"  <br/> |4-6  <br/> |Logitech C930e  <br/> Logitech 頻道  <br/> Logitech BRIO  <br/> Logitech PTZ Pro  <br/> Polycom MSR  <br/> Polycom CX5100  <br/> |Logitech PTZ Pro 通常與 Logitech 群組捆綁  <br/> |
|**深淺** <br/> 18 "x 20"  <br/> |6-12  <br/> |Logitech 頻道  <br/> Logitech BRIO  <br/> Logitech PTZ Pro  <br/> Polycom MSR  <br/> Polycom CX5100  <br/> ||
|**大中型** <br/> 15 "x 32"  <br/> |12-16  <br/> |Logitech PTZ Pro  <br/> Polycom MSR  <br/> Polycom CX5100  <br/> ||

 > [!NOTE]
 > 房間顯示解析度的前面應該設定為 [不超過 1920x1080p]。

## <a name="required-software-downloads"></a>所需的軟體下載

若要建立您自己的 Microsoft 團隊聊天室圖像, 請依照[設定 Microsoft 團隊聊天室主控台](console.md)中的指示進行。 這些指示將引導您下載安裝程式所需的所有軟體。 

> [!NOTE]
> IT 專業人員必須透過大量授權協定, 才能存取 Windows 10 企業版 ISO 檔案。

此外, 您可能會想要使用[SkypeRoomProvisioningScript. ps1](https://go.microsoft.com/fwlink/?linkid=870105)的複本, 您可以用來提供 Microsoft 團隊聊天室帳戶。

## <a name="see-also"></a>另請參閱
[流覽所有捆綁包](https://products.office.com/en-us/microsoft-teams/across-devices/devices)

[規劃 Microsoft 團隊聊天室](skype-room-systems-v2-0.md)

[部署 Microsoft 團隊聊天室](room-systems-v2.md)

[設定 Microsoft 團隊聊天室主控台](console.md)

[管理 Microsoft 團隊聊天室](skype-room-systems-v2.md)

[商務用 Skype 附加元件授權](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)
