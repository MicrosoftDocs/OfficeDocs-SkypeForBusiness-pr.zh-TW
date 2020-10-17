---
title: Lync Server 2013：分支網站恢復功能
description: Lync Server 2013：分支網站恢復功能。
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
ms.openlocfilehash: a498751ce99d0e8e85d6cbe53915c864e64440bd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552199"
---
# <a name="branch-site-resiliency-features-in-lync-server-2013"></a>Lync Server 2013 中的分支網站恢復功能

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-10_

如果您提供分支網站恢復能力，當分支網站與中央網站的 WAN 連線失敗，或是無法存取中央網站時，下列語音功能應該仍然可用：

<div>


  - 輸入和輸出公用交換電話網路 (PSTN) 通話

  - 相同與不同的網站之間的使用者，皆可進行企業通話

  - 基本通話處理，包括通話保留、取回和轉接

  - 兩方立即訊息

  - 來電轉接、端點同時響鈴、呼叫委派及小組通話服務，但只有在 delegator 和代理人 (例如，管理員和管理員的系統管理員) 或所有小組成員，都是在相同的網站上設定

  - Cdr)  (詳細通話記錄

  - 使用會議自動語音應答的 PSTN 電話撥入式會議

  - 語音信箱功能（如果您設定語音信箱重新路由設定）。  (如需詳細資訊，請參閱 [Lync Server 2013 的分支網站恢復需求](lync-server-2013-branch-site-resiliency-requirements.md)。 ) 

  - 使用者驗證和授權

下列功能只有在您的恢復解決方案在分支網站上是完整的 Lync Server 部署時才會使用：

  - IM、web 及 A/V 會議

  - 目前狀態和請勿打擾 (DND) 型路由 (禁止通話在已啟用 DND 的分機上響鈴) 

  - 更新來電轉接設定

  - 回應群組應用程式和通話駐留應用程式

  - 布建新的電話和用戶端，但只有在分支網站有 Active Directory 網域服務。

  - 增強型 9-1-1 (E9-1-1) 
    
    如果已部署 E9-1-1，而中央網站的 SIP 主幹無法使用，因為 WAN 連結已關機，則 Survivable Branch 裝置會將 E9-1-1 呼叫路由傳送至本機分支閘道。 若要啟用此功能，分支網站使用者的語音原則應該會在發生 WAN 失敗時，將通話路由傳送至本地閘道。

<div>


> [!NOTE]  
> SBA (survivable branch office) 不支援 XMPP。 位於 SBA 設定中的使用者將無法使用 XMPP 連絡人傳送 IMs 或查看顯示狀態。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

