---
title: 定義手動取得位置的使用者體驗
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the user experience for manually acquiring a location
ms:assetid: d37f67d3-e248-483b-b64c-3986559ef357
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398912(v=OCS.15)
ms:contentKeyID: 48185435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0fa9c7242351417c4ea82ed7ce6183963bc9730e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504470"
---
# <a name="defining-the-user-experience-for-manually-acquiring-a-location-in-lync-server-2013"></a>定義在 Lync Server 2013 中手動取得位置的使用者體驗

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-03_

如果用戶端位於網路之外，或是未定義的子網中，使用者可以手動輸入位置。 不過，在緊急通話期間，來電會先路由傳送到國家/地區 E9-1-1 緊急呼叫回應中心 (ECRC) dispatcher，再路由傳送至公用安全回應點 (PSAP) 。 ECRC 會口頭查詢位置的來電者，然後根據提供的資訊，將通話轉寄給適當的 PSAP。

  - **當使用者未自動提供位置資訊服務時，是否要提示使用者輸入位置？**  
    例如，如果用戶端位於未定義的子網、家裡、酒店或網路以外的其他地方，是否應使用者輸入位置？
    
    您可以在位置原則中設定 [ **必要的位置** ] 設定，以定義用戶端行為。 將此值設為 [否] 表示將不會提示使用者輸入位置。 將此值設為 [是]，表示系統會提示使用者輸入位置，但可以關閉提示。 將此值設為免責聲明表示將會提示使用者輸入位置，如果使用者嘗試關閉提示，將會顯示免責聲明。 在所有情況下，使用者都可以繼續照常使用用戶端。

當使用者手動輸入位置時，該位置會對應至用戶端網路之預設閘道的 MAC 位址，並儲存在用戶端的每一位使用者資料表中。 當使用者回到任何先前儲存的位置時，Lync 用戶端會自動將自己設定到該位置。

<div>


> [!NOTE]
> 您可以只修改用戶端的目前位置，但也可以刪除儲存在本機使用者資料表中的任何位置。



</div>

</div>

<span> </span>

</div>

</div>

</div>

