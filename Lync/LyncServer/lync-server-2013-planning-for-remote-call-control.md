---
title: Lync Server 2013：規劃遠端通話控制
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
ms.openlocfilehash: b4c07674be037c7d2fe06d6e2811dcd3264cc6db
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725223"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-remote-call-control-in-lync-server-2013"></a>在 Lync Server 2013 中規劃遠端通話控制

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-05_

在 Lync Server 2013 中，遠端通話控制案例的支援可讓使用者在其桌上型電腦上使用 Lync 2013 控制其私人分支 exchange （PBX）電話。 本節說明部署遠端通話控制的遠端呼叫控制功能與需求。

在 PBX 和 Lync Server 2013 之間整合，可讓遠端呼叫控制的使用者使用 Lync 2013 使用者介面（UI），透過下列方式控制其 PBX 手機上的呼叫：

<div>


> [!NOTE]  
> 最終，託管使用者 PBX 手機的 PBX 功能決定該使用者可以使用的遠端呼叫控制功能。



</div>

  - 撥打撥出電話

  - 接聽來電

  - 使用立即訊息接聽來電
    
    <div>
    

    > [!NOTE]  
    > 也就是說，當來電者的電話號碼可以與組織全域通訊清單（GAL）中的立即訊息位址相關聯，請在被叫方的 Lync 連絡人清單中，或在聯盟夥伴的組織中。

    
    </div>

  - 轉接來電

  - 轉接來電

  - 保留通話

  - 在多個併發通話間切換

  - 接聽通話中的第二個通話（也就是通話等待）

  - 撥號雙音調 multifrequency （DTMF）位數

  - 在交談視窗中，在 Microsoft Office OneNote 筆記記錄程式中輸入記事

此外，當使用者啟用 [遠端通話控制] 時，Lync 2013 會為使用者提供下列通話資訊：

  - 來電者的電話號碼在遠端呼叫控制啟用使用者的 Microsoft Office Outlook [訊息與共同作業用戶端]、[Lync 連絡人清單] 或貴組織的 GAL 中的 [連絡人] 清單中存在的名稱。

  - 過去的撥入和撥出通話，會儲存在 Outlook 中的 [交談記錄] 資料夾中。

  - 未接來電通知會傳送到使用者的 Outlook [收件匣] 資料夾，但只有在收到來電時，才會產生 Lync。

<div>

## <a name="remote-call-control-and-enterprise-voice"></a>遠端通話控制和企業語音

雖然遠端通話控制功能是與企業語音功能分開的，而且不能同時為使用者啟用，但企業語音也提供可供啟用遠端呼叫控制的使用者使用的功能子集。 如果已部署企業語音，則已啟用遠端通話控制的使用者可以使用 Lync 來存取下列企業語音功能：

  - 撥打及接聽其他 Lync 用戶端的語音通話

  - 加入由啟用企業語音的使用者所建立之會議的音訊部分

</div>

<div>

## <a name="in-this-section"></a>本節內容

  - [Lync Server 2013 中遠端呼叫控制的部署工作](lync-server-2013-deployment-tasks-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

