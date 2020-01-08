---
title: Lync Server 2013：驗證語音號碼標準化與路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Validating voice number normalization and routing
ms:assetid: a6a825c7-6928-4e80-b7e9-803b7f7ebd13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720922(v=OCS.15)
ms:contentKeyID: 63969633
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1be8f09304ccf077eb24daf707e536e9c90f84dd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978146"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-voice-number-normalization-and-routing-in-lync-server-2013"></a>驗證 Lync Server 2013 中的語音號碼標準化與路由

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-05-19_

正確的數位正常化與路由對於企業語音環境而言非常重要。 特別是在從專用分支 exchange （PBX）遷移到獨立的 Lync Server 環境時，成功遷移的其中一個金鑰就是顯示並記錄所有現有的撥號規則，並建立適當的正常化規則、語音原則[電話使用方式] 和 [路線]。

驗證編號正常化與路由不僅在遷移期間很重要，而且在系統的正常執行中也很重要。

我們建議您每天使用 Lync Server [控制台] 進行這項驗證，從針對 Lync Server 全域設定中發佈的目前正常化規則開發一組強健的測試案例開始。 這些測試案例應該每日執行，以醒目提示已作出並提交給撥號方案的任何不想要的變更。

Lync Server [控制台] 也可協助您視覺化、測試、變更、封存及共用有關語音路由與變更企業語音數位正常化規則、撥號方案、語音原則及路線的設定資訊。 它還有其他功能可讓您執行下列作業：

  - 在系統之間匯出及匯入或備份語音路由資料。

  - 在將配置變更上傳至實際系統之前先進行測試。

  - 建立並執行配置測試案例，以協助確保在進行變更之後，路由資料的可用性，但在向已部署的系統提交變更之前。

  - 建立及變更數位正常化規則、位置設定檔、語音原則及路由資料，而不需要撰寫必要的一般運算式。

  - 分析位置設定檔與 Lync Server Phone Edition 的相容性。

  - 您可以在[Lync Server 2013 的測試語音路由中](lync-server-2013-test-voice-routing.md)找到更多關於語音路由測試的資訊

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中測試語音路由](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

