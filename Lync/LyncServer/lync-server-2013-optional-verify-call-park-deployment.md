---
title: Lync Server 2013：（選用）驗證通話駐留部署
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: (Optional) Verify Call Park deployment
ms:assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413076(v=OCS.15)
ms:contentKeyID: 48185952
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 110617bbd77da0efb8802c6aba401f2ea5075b01
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981659"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-verify-call-park-deployment-in-lync-server-2013"></a>可選在 Lync Server 2013 中確認通話駐留部署

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-11_

安裝並設定 [通話駐留] 之後，您必須驗證設定，以確保停車場和檢索通話如期運作。 至少請確認下列事項：

  - 呼叫已啟用通話駐留且使用者寄存通話的使用者。
    
    <div>
    

    > [!NOTE]  
    > 如果您在執行此測試前，在語音原則中啟用通話駐留，停用通話的使用者需要登出 Lync Server，然後重新登入，才能在轉移通話清單中看到通話寄存選項。

    
    </div>

  - 撥打軌道數位以取得通話。

  - 停用另一個通話，讓撥出通話超時，而且不要挑選 ringback。 確認超時通話正確地路由至指定給**OnTimeoutURI**的回退目的地。

</div>

<span> </span>

</div>

</div>

</div>

