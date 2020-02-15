---
title: Lync Server 2013： 規劃遠端通話控制
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
ms.openlocfilehash: 7a2faff08d5517809d4cfb11d00711a146accc61
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050725"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-remote-call-control-in-lync-server-2013"></a>規劃 Lync Server 2013 中的遠端呼叫控制

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-05_

在 [Lync Server 2013 支援遠端呼叫控制案例可讓使用者在其桌面的電腦上使用 Lync 2013 控制其專用交換機 (pbx) 電話。 本節說明遠端呼叫控制功能，以及部署遠端呼叫控制的需求。

PBX 與 Lync Server 2013 之間的整合可讓使用者啟用遠端呼叫控制，可使用 Lync 2013 使用者介面 (UI) 以下列方式控制 PBX 電話上的通話：

<div>


> [!NOTE]  
> 最終，主控使用者之 PBX 電話的 PBX 功能可決定該使用者可使用的遠端呼叫控制功能。



</div>

  - 撥出電話

  - 接聽來電

  - 使用立即訊息接聽來電
    
    <div>
    

    > [!NOTE]  
    > 也就是說，當來電者的電話號碼可以是貴組織的全域通訊清單 (GAL)、 在受話者的 Lync 連絡人清單中，或同盟的協力廠商組織中的立即訊息位址相關聯。

    
    </div>

  - 轉接電話

  - 轉接來電

  - 保留通話

  - 切換多個並行通話

  - 在通話時接聽第二個通話 (即插撥)

  - 撥打複頻式訊號 (DTMF) 數字

  - 在 [交談] 視窗中，於 Microsoft Office OneNote 筆記記錄程式中輸入記事

此外，當使用者啟用遠端呼叫控制，Lync 2013 提供使用者，並將下列通話資訊：

  - 識別來電者依名稱當來電者的電話號碼存在於 [連絡人] 清單的遠端呼叫控制功能之使用者的 Microsoft Office Outlook 訊息和共同作業用戶端、 Lync 連絡人] 清單中或貴組織的 GAL。

  - 過去的來電及撥出電話 (儲存至 Outlook 的 [交談記錄] 資料夾中)。

  - 未接來電通知傳送給使用者的 Outlook 收件匣] 資料夾，但是 Lync 正在執行時接收到來電時，才會產生。

<div>

## <a name="remote-call-control-and-enterprise-voice"></a>遠端呼叫控制及　Enterprise Voice

雖然遠端呼叫控制功能是分開 Enterprise Voice 功能，且使用者無法啟用兩者皆適用，Enterprise Voice 會提供功能也可設定已啟用遠端呼叫控制使用者的子集。 如果部署企業語音時，已啟用遠端呼叫控制使用者可以使用 Lync 來存取下列 Enterprise Voice 功能：

  - 撥打及接聽另一個 Lync 用戶端的音訊通話

  - 加入啟用 Enterprise voice 使用者所建立會議的音訊部分

</div>

<div>

## <a name="in-this-section"></a>本章節內容

  - [Lync Server 2013 中的遠端呼叫控制的部署工作](lync-server-2013-deployment-tasks-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

