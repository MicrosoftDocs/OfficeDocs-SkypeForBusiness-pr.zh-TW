---
title: Lync Server 2013： 分支網站彈性功能
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
ms.openlocfilehash: 5787f0fd07afcf0ca70a9c3b0f7c21e3525cfae7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150722"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-features-in-lync-server-2013"></a>Lync Server 2013 中的分支網站恢復功能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-02-10_

如果您提供分支網站恢復能力，如果分支站台的 WAN 連線至中央網站失敗或無法連線到中央網站時，以下語音功能應可繼續運作：

<div>


  - 輸入和輸出公用交換的電話網路 (PSTN) 通話

  - 相同與不同的網站之間的使用者，皆可進行企業通話

  - 基本通話處理，包括通話保留、取回和轉接

  - 若為雙方立即訊息

  - 來電轉接、 同時響鈴端點、 通話委派及小組通話服務，但僅限委託人和代理人 （例如，經理和經理的系統管理員） 或所有小組成員，在相同站台設定

  - 詳細通話記錄 (Cdr)

  - PSTN 電話撥入式會議與會議自動語音應答

  - 語音信箱功能，如果您設定語音信箱重新路由設定。 （如需詳細資訊，請參閱[Lync Server 2013 的分支網站恢復能力需求](lync-server-2013-branch-site-resiliency-requirements.md)）。

  - 使用者驗證和授權

下列功能會變成可用只有在您的恢復解決方案為分支網站的完整規模 Lync Server 部署：

  - IM、 web 和 A / V 會議

  - 目前狀態和不打擾 DND 基礎路由 （可防止來電在已啟動 DND 的分機上響起）

  - 更新來電轉接設定

  - 回應群組應用程式和通話駐留應用程式

  - 佈建新電話與用戶端，但是只有 Active Directory 網域服務有分支網站。

  - 增強型的 9-1-1 (E9-1-1)
    
    如果部署 E9-1-1，且 SIP 主幹在中央網站無法使用，因為在 WAN 連結已關閉，Survivable Branch Appliance 會路由傳送至本機分支閘道的 E9-1-1 通話。 若要啟用此功能，在分支網站使用者的語音原則應該將通話路由傳送至本機閘道 WAN 故障時。

<div>


> [!NOTE]  
> 不支援 XMPP 的 SBA (survivable branch office)。 使用者位於 SBA 設定將無法傳送 Im 或查看與 XMPP 連絡人的目前狀態。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

