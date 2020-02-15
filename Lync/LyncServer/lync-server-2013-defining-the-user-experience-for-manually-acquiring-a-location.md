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
ms.openlocfilehash: 56cb653b1058bd73cf57842d77b734a9e96eaf10
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045876"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-the-user-experience-for-manually-acquiring-a-location-in-lync-server-2013"></a><span data-ttu-id="60cd6-102">定義手動取得位置 Lync Server 2013 中的使用者經驗</span><span class="sxs-lookup"><span data-stu-id="60cd6-102">Defining the user experience for manually acquiring a location in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60cd6-103">_**主題上次修改日期：** 2012年-10-03_</span><span class="sxs-lookup"><span data-stu-id="60cd6-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="60cd6-104">如果用戶端位於外部網路，或在 [定義的子網路，使用者可以手動輸入位置。</span><span class="sxs-lookup"><span data-stu-id="60cd6-104">If a client is located outside the network, or in an undefined subnet, the user can manually enter a location.</span></span> <span data-ttu-id="60cd6-105">但期間，緊急通話，通話會先被路由傳送至國家/區域 E9-1-1 緊急通話回應中心 (ECRC) 發送程式之前路由傳送到公用安全回應點 (PSAP)。</span><span class="sxs-lookup"><span data-stu-id="60cd6-105">But during an emergency call, the call will first be routed to a national/regional E9-1-1 Emergency Call Response Center (ECRC) dispatcher before being routed to a Public Safety Answering Point (PSAP).</span></span> <span data-ttu-id="60cd6-106">ECRC 將口頭查詢來電者輸入位置，然後將通話轉接至適當的 PSAP，根據所提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="60cd6-106">The ECRC will verbally query the caller for a location and then forward the call to the appropriate PSAP, based on the information provided.</span></span>

  - <span data-ttu-id="60cd6-107">**是否應提示使用者輸入位置，當一個未自動提供位置資訊服務？**</span><span class="sxs-lookup"><span data-stu-id="60cd6-107">**Should users be prompted to enter a location when one is not automatically provided by the Location Information service?**</span></span>  
    <span data-ttu-id="60cd6-108">例如，如果用戶端位於中定義的子網路、 在家中、 旅館或網路外的任何其他地方，應該使用者必須輸入位置？</span><span class="sxs-lookup"><span data-stu-id="60cd6-108">For example, if a client is located in an undefined subnet, at home, in a hotel, or anywhere else outside the network, should the user be required to enter a location?</span></span>
    
    <span data-ttu-id="60cd6-109">您可以定義的用戶端行為的位置原則中設定的**位置所需**的設定。</span><span class="sxs-lookup"><span data-stu-id="60cd6-109">You can configure the **Location Required** setting in the location policy to define the client behavior.</span></span> <span data-ttu-id="60cd6-110">將此值設定為，使用者將不會提示輸入位置不表示。</span><span class="sxs-lookup"><span data-stu-id="60cd6-110">Setting this value to No means that the user will not be prompted for a location.</span></span> <span data-ttu-id="60cd6-111">設定此值設為 [是] 表示 [位置]，系統會提示使用者，但可以解除提示。</span><span class="sxs-lookup"><span data-stu-id="60cd6-111">Setting this value to Yes means that the user will be prompted for a location, but can dismiss the prompt.</span></span> <span data-ttu-id="60cd6-112">設定免責聲明這個值表示使用者將會提示輸入位置，並且會顯示免責聲明如果使用者嘗試解除提示。</span><span class="sxs-lookup"><span data-stu-id="60cd6-112">Setting this value to Disclaimer means that the user will be prompted for a location, and will be shown a disclaimer if they try to dismiss the prompt.</span></span> <span data-ttu-id="60cd6-113">在所有情況下，使用者可以繼續使用用戶端像平常一樣。</span><span class="sxs-lookup"><span data-stu-id="60cd6-113">In all cases, the user can continue to use the client as usual.</span></span>

<span data-ttu-id="60cd6-114">當使用者手動輸入位置時，位置會對應至用戶端的網路的預設閘道的 MAC 位址，並儲存在位於用戶端上的每位使用者資料表中。</span><span class="sxs-lookup"><span data-stu-id="60cd6-114">When a user manually enters a location, the location is mapped to the MAC address of the default gateway of the client’s network, and is stored in a per-user table located on the client.</span></span> <span data-ttu-id="60cd6-115">當使用者傳回至任何先前已儲存的位置時，Lync 用戶端會自動設定本身至該位置。</span><span class="sxs-lookup"><span data-stu-id="60cd6-115">When the user returns to any previously stored location, the Lync client automatically sets itself to that location.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="60cd6-116">您可以修改您的用戶端的目前位置，但您也可以刪除本機使用者資料表中儲存的任何位置。</span><span class="sxs-lookup"><span data-stu-id="60cd6-116">You can modify only the current location of your client, but you can also delete any location stored in the local user’s table.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

