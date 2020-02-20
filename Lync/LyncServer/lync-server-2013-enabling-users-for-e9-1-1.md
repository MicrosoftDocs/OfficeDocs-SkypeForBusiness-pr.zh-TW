---
title: Lync Server 2013： 為使用者啟用 E9-1-1
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling users for E9-1-1
ms:assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425892(v=OCS.15)
ms:contentKeyID: 48183884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5550ec608b34b66a3e47ceb4535dd23ca7c9a7f1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146346"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-users-for-e9-1-1-in-lync-server-2013"></a>為使用者啟用 E9-1-1 在 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-06-06_

在用戶端註冊期間 Lync Server 會使用位置原則來設定已啟用 Enterprise Voice 的使用者的 E9-1-1 屬性。 此原則包含的設定會定義 E9-1-1 實作方式。 例如，「 位置原則包含資訊，例如緊急撥號對應表的字串，而不論使用者必須手動輸入位置，如果將位置資訊服務不會自動提供一。 位置原則的完整定義，請參閱[定義 Lync Server 2013 的位置原則](lync-server-2013-defining-the-location-policy.md)。

Lync Server 可以指派位置原則，子網路為基礎的用戶端或使用者根據全域、 每個網站或個別使用者原則。 如需判斷該如何啟用使用者，請先回答下列問題。

  - **您打算啟用所有使用者，還是打算將支援範圍限定在企業的特定地理區域？**  
    您可以使用通用位置原則，將某個位置指派給企業中所有的使用者。 不過，藉由將位置原則指派給 Lync Server 網路網站，並再將子網路新增至網站，您可以限制 E9-1-1 支援在企業內的選取位置，並指定 E9-1-1 的路由傳送行為以每個網站為基礎。

<!-- end list -->

  - **您是否打算透過使用者原則啟用個別使用者？**  
    如果您想自訂使用者的 E9-1-1 支援，可以直接指派位置原則給特定使用者或公共區域電話連絡人物件。

<!-- end list -->

  - **當用戶端漫遊至網路外，或從未定義的子網路連線時，是否仍應啟用用戶端的 E9-1-1？**  
    如果使用者指派全域、 網站，或個別使用者位置原則，他們可能需要手動輸入到用戶端的位置，如果用戶端不是位於內定義的子網路或位置資訊服務已找到任何位置。 如需詳細資訊，請參閱[定義手動取得位置 Lync Server 2013 中的使用者經驗](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md)。

</div>

<span> </span>

</div>

</div>

</div>

