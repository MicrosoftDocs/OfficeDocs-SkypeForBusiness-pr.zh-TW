---
title: Lync Server 2013：規劃遠端呼叫控制
description: Lync Server 2013：規劃遠端呼叫控制。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for remote call control
ms:assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558658(v=OCS.15)
ms:contentKeyID: 48184371
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e3a089a806683098a948d235559bbcb16224bdde
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564689"
---
# <a name="planning-for-remote-call-control-in-lync-server-2013"></a>在 Lync Server 2013 中規劃遠端呼叫控制

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-05_

在 Lync Server 2013 中，支援遠端呼叫控制案例，可讓使用者在其桌上型電腦上使用 Lync 2013 來控制其專用的分支 exchange (PBX) 電話。 本節說明遠端呼叫控制功能，以及部署遠端呼叫控制的需求。

PBX 和 Lync Server 2013 之間的整合，可讓啟用遠端呼叫控制的使用者使用 Lync 2013 使用者介面 (UI) 以下列方式控制 PBX 電話上的通話：

<div>


> [!NOTE]  
> 最終，主控使用者之 PBX 電話的 PBX 功能可決定該使用者可使用的遠端呼叫控制功能。



</div>

  - 撥出電話

  - 接聽來電

  - 使用立即訊息接聽來電
    
    <div>
    

    > [!NOTE]  
    > 亦即，當來電者的電話號碼可以與您組織的全域通訊清單中的立即訊息位址相關聯 (GAL) 、被叫用的 Lync 連絡人清單，或同盟協力廠商的組織中。

    
    </div>

  - 轉接電話

  - 轉接來電

  - 保留通話

  - 切換多個並行通話

  - 在通話時接聽第二個通話 (即插撥)

  - 撥打複頻式訊號 (DTMF) 數字

  - 在 [交談] 視窗中，於 Microsoft Office OneNote 筆記記錄程式中輸入記事

此外，當使用者啟用遠端呼叫控制時，Lync 2013 會為使用者提供下列呼叫資訊：

  - 來電者的電話號碼存在於啟用遠端呼叫控制功能之使用者的 Microsoft Office Outlook 郵件和共同作業用戶端、Lync 連絡人清單或您組織的 GAL 中的連絡人清單中時，會以名稱識別來電者。

  - 過去的來電及撥出電話 (儲存至 Outlook 的 [交談記錄] 資料夾中)。

  - 未接來電通知，它會傳送至使用者的 Outlook [收件匣] 資料夾，但只有在接收來電時，才會產生 Lync。

<div>

## <a name="remote-call-control-and-enterprise-voice"></a>遠端呼叫控制及　Enterprise Voice

雖然遠端呼叫控制功能與 Enterprise Voice 功能不同，而且不能同時啟用使用者，但 Enterprise Voice 提供的功能子集也可供啟用遠端呼叫控制的使用者使用。 如果部署了 Enterprise Voice，已啟用遠端呼叫控制的使用者可以使用 Lync 來存取下列 Enterprise Voice 功能：

  - 撥打和接收其他 Lync 用戶端的音訊通話

  - 加入由已啟用 Enterprise Voice 之使用者所建立之會議的音訊部分

</div>

<div>

## <a name="in-this-section"></a>本章節內容

  - [Lync Server 2013 中遠端呼叫控制的部署工作](lync-server-2013-deployment-tasks-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

