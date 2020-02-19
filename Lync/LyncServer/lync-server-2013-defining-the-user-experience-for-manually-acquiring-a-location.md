---
title: 定義手動取得位置的使用者經驗
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
ms.openlocfilehash: 20bd88f9c9f619e67c9aec8f6b0111320fa3ed2d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135139"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-the-user-experience-for-manually-acquiring-a-location-in-lync-server-2013"></a>定義手動取得位置 Lync Server 2013 中的使用者經驗

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-03_

如果用戶端位於外部網路，或在 [定義的子網路，使用者可以手動輸入位置。 但期間，緊急通話，通話會先被路由傳送至國家/區域 E9-1-1 緊急通話回應中心 (ECRC) 發送程式之前路由傳送到公用安全回應點 (PSAP)。 ECRC 將口頭查詢來電者輸入位置，然後將通話轉接至適當的 PSAP，根據所提供的資訊。

  - **是否應提示使用者輸入位置，當一個未自動提供位置資訊服務？**  
    例如，如果用戶端位於中定義的子網路、 在家中、 旅館或網路外的任何其他地方，應該使用者必須輸入位置？
    
    您可以定義的用戶端行為的位置原則中設定的**位置所需**的設定。 將此值設定為，使用者將不會提示輸入位置不表示。 設定此值設為 [是] 表示 [位置]，系統會提示使用者，但可以解除提示。 設定免責聲明這個值表示使用者將會提示輸入位置，並且會顯示免責聲明如果使用者嘗試解除提示。 在所有情況下，使用者可以繼續使用用戶端像平常一樣。

當使用者手動輸入位置時，位置會對應至用戶端的網路的預設閘道的 MAC 位址，並儲存在位於用戶端上的每位使用者資料表中。 當使用者傳回至任何先前已儲存的位置時，Lync 用戶端會自動設定本身至該位置。

<div>


> [!NOTE]
> 您可以修改您的用戶端的目前位置，但您也可以刪除本機使用者資料表中儲存的任何位置。



</div>

</div>

<span> </span>

</div>

</div>

</div>

