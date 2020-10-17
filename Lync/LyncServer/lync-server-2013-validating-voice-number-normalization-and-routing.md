---
title: Lync Server 2013：驗證語音號碼正常化和路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating voice number normalization and routing
ms:assetid: a6a825c7-6928-4e80-b7e9-803b7f7ebd13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720922(v=OCS.15)
ms:contentKeyID: 63969633
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d8d68dfaaca20d991aa37d1a73ae31bf88f5c31
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518720"
---
# <a name="validating-voice-number-normalization-and-routing-in-lync-server-2013"></a>在 Lync Server 2013 中驗證語音號碼正常化和路由

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-05-19_

正確的數位正規化和路由對功能性 Enterprise Voice 環境而言非常重要。 尤其是在從專用交換機遷移 (PBX) 到獨立的 Lync Server 環境時，成功遷移的其中一個按鍵是顯示並記錄所有現有的撥號規則，並建立適當的正規化規則、語音原則、電話使用方式和路由。

驗證編號正規化和路由是很重要的，不僅在遷移期間，也不是系統的一般穩定作業。

我們建議您每日使用 Lync Server 控制台，以針對在 Lync Server 全域設定中所發佈的目前正規化規則集開發一組強大的測試案例開始，進行此驗證。 應該每日執行這些測試案例，以反白顯示對撥號對應表進行的任何不需要的變更。

Lync Server 控制台也可協助您視覺化、測試、變更、封存和共用語音路由的設定資訊，以及變更企業語音號碼正規化規則、撥號對應表、語音原則和路由。 其還有其他功能可供您執行下列作業：

  - 在系統之間匯出及匯入或備份語音路由資料。

  - 先測試設定變更，再將其上傳至實際系統。

  - 建立及執行設定測試案例，以協助確保在您對已部署的系統進行變更之後，路由資料的可用性。

  - 建立及變更編號正規化規則、位置設定檔、語音原則及路由資料，而不需撰寫必要的正則運算式。

  - 分析位置設定檔與 Lync Server Phone Edition 的相容性。

  - [在 Lync Server 2013 的測試語音路由中](lync-server-2013-test-voice-routing.md)，可以找到有關語音路由測試的詳細資訊

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中測試語音路由](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

