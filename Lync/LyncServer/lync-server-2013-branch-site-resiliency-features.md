---
title: Lync Server 2013：分支網站彈性功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency features
ms:assetid: 8e3feda5-9a38-4e3c-b808-af29f19c5eb9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398715(v=OCS.15)
ms:contentKeyID: 48184765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a490de36322914235346cbc141784aab2c24f2ce
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737563"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-features-in-lync-server-2013"></a>Lync Server 2013 中的分支網站彈性功能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-10_

如果您提供分支網站復原功能，且分支網站與中央網站的 WAN 連線失敗，或是無法取得中心網站，下列語音功能應該會繼續提供：

<div>


  - 輸入和輸出公用電話網絡（PSTN）通話

  - 在相同網站和兩個不同網站之間的使用者之間的企業通話

  - 基本呼叫處理，包括呼叫保留、檢索及轉移

  - 二方立即訊息

  - 來電轉接、同時撥打端點、呼叫委派及小組通話服務，但僅限在相同的網站上設定 delegator 與代理人（例如，主管和主管管理員）或所有團隊成員

  - 通話明細記錄（CDRs）

  - 含會議自動助理的 PSTN 電話撥入式會議

  - 語音信箱功能（如果您設定 [語音信箱重新路由設定]）。 （如需詳細資訊，請參閱[Lync Server 2013 的分支網站復原需求](lync-server-2013-branch-site-resiliency-requirements.md)）。

  - 使用者驗證與授權

只有當您的復原方案是分支網站上的完整 Lync Server 部署時，才能使用下列功能：

  - IM、網站和 A/V 會議

  - [目前狀態] 和 [請勿打擾（DND）] 路由（在這種情況下，禁止通話在已 DND 啟用的分機上響鈴）

  - 更新來電轉接設定

  - 回應群組應用程式及通話駐留應用程式

  - 提供新的手機和用戶端，但只有在分支網站中存在 Active Directory 網域服務時才有這個功能。

  - 增強型9-1-1 （E9-1-1）
    
    如果已部署 E9-1-1，且中央網站上的 SIP 幹線無法使用，因為 WAN 連結已關閉，所以 Survivable 分支裝置會將 E9-1-1 呼叫路由到本機分支閘道。 若要啟用此功能，分支網站使用者的語音原則應該在 WAN 發生故障時將呼叫路由到本機閘道。

<div>


> [!NOTE]  
> XMPP 不支援 SBA （survivable branch office）。 駐留在 SBA 配置中的使用者將無法使用 XMPP 連絡人傳送 Im 或查看目前狀態。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

