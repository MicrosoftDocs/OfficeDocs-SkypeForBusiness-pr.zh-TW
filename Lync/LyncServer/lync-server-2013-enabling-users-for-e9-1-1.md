---
title: Lync Server 2013：啟用 E9-1-1 版使用者
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling users for E9-1-1
ms:assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425892(v=OCS.15)
ms:contentKeyID: 48183884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d62d811d78695cbc04fa8def76da1843beddb586
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977276"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-users-for-e9-1-1-in-lync-server-2013"></a>在 Lync Server 2013 中啟用 E9-1-1 的使用者

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-06_

在用戶端註冊期間，Lync Server 會使用位置原則來設定企業語音使用者的 E9 屬性。 此原則包含定義如何執行 E9-1-1 的設定。 例如，位置原則包含緊急撥號字串等資訊，以及如果位置資訊服務不會自動提供某個位置，是否需要使用者手動輸入位置。 如需位置原則的完整定義，請參閱[定義 Lync Server 2013 的位置原則](lync-server-2013-defining-the-location-policy.md)。

Lync Server 可以根據子網來指派位置策略給客戶，或是根據全域、每個網站或每個使用者的原則，指派給使用者。 若要協助您決定將如何啟用使用者，您應該先回答下列問題。

  - **您是否計畫要啟用所有使用者，或限制對企業特定地理區域的支援？**  
    您可以使用全域位置原則，將位置指派給企業中的所有使用者。 不過，若要將位置原則指派給 Lync Server 網路網站，然後將子網新增至網站，您可以將 E9-1-1 支援限制在企業內所選的位置，並在每個網站上指定 E9 的路由行為。

<!-- end list -->

  - **您是否計畫透過使用者原則啟用個別使用者？**  
    如果您想要自訂 E9-1-1 支援，您可以將位置原則直接指派給特定的使用者或常見的區域電話連絡人物件。

<!-- end list -->

  - **當用戶端在網路外部漫遊或從未定義的子網進行連線時，如果用戶端仍在 E9-1-1，就應該啟用用戶端嗎？**  
    如果將使用者指派為全域、網站或每位使用者的位置原則，當用戶端不在已定義的子網中，或位置資訊服務找不到任何位置時，可能需要他們手動在用戶端中輸入位置。 如需詳細資訊，請參閱[定義在 Lync Server 2013 中手動取得位置的使用者體驗](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md)。

</div>

<span> </span>

</div>

</div>

</div>

