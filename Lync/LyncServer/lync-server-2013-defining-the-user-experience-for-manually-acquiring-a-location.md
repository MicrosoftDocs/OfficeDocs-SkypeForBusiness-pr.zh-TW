---
title: 定義手動取得位置的使用者體驗
description: 定義手動取得位置的使用者體驗。
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
ms.openlocfilehash: 74e4a399e8010cfc22430216ef6e3c11fc9a7bdc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567549"
---
# <a name="defining-the-user-experience-for-manually-acquiring-a-location-in-lync-server-2013"></a><span data-ttu-id="69293-103">定義在 Lync Server 2013 中手動取得位置的使用者體驗</span><span class="sxs-lookup"><span data-stu-id="69293-103">Defining the user experience for manually acquiring a location in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69293-104">_**主題上次修改日期：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="69293-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="69293-105">如果用戶端位於網路之外，或是未定義的子網中，使用者可以手動輸入位置。</span><span class="sxs-lookup"><span data-stu-id="69293-105">If a client is located outside the network, or in an undefined subnet, the user can manually enter a location.</span></span> <span data-ttu-id="69293-106">不過，在緊急通話期間，來電會先路由傳送到國家/地區 E9-1-1 緊急呼叫回應中心 (ECRC) dispatcher，再路由傳送至公用安全回應點 (PSAP) 。</span><span class="sxs-lookup"><span data-stu-id="69293-106">But during an emergency call, the call will first be routed to a national/regional E9-1-1 Emergency Call Response Center (ECRC) dispatcher before being routed to a Public Safety Answering Point (PSAP).</span></span> <span data-ttu-id="69293-107">ECRC 會口頭查詢位置的來電者，然後根據提供的資訊，將通話轉寄給適當的 PSAP。</span><span class="sxs-lookup"><span data-stu-id="69293-107">The ECRC will verbally query the caller for a location and then forward the call to the appropriate PSAP, based on the information provided.</span></span>

  - <span data-ttu-id="69293-108">**當使用者未自動提供位置資訊服務時，是否要提示使用者輸入位置？**</span><span class="sxs-lookup"><span data-stu-id="69293-108">**Should users be prompted to enter a location when one is not automatically provided by the Location Information service?**</span></span>  
    <span data-ttu-id="69293-109">例如，如果用戶端位於未定義的子網、家裡、酒店或網路以外的其他地方，是否應使用者輸入位置？</span><span class="sxs-lookup"><span data-stu-id="69293-109">For example, if a client is located in an undefined subnet, at home, in a hotel, or anywhere else outside the network, should the user be required to enter a location?</span></span>
    
    <span data-ttu-id="69293-110">您可以在位置原則中設定 [ **必要的位置** ] 設定，以定義用戶端行為。</span><span class="sxs-lookup"><span data-stu-id="69293-110">You can configure the **Location Required** setting in the location policy to define the client behavior.</span></span> <span data-ttu-id="69293-111">將此值設為 [否] 表示將不會提示使用者輸入位置。</span><span class="sxs-lookup"><span data-stu-id="69293-111">Setting this value to No means that the user will not be prompted for a location.</span></span> <span data-ttu-id="69293-112">將此值設為 [是]，表示系統會提示使用者輸入位置，但可以關閉提示。</span><span class="sxs-lookup"><span data-stu-id="69293-112">Setting this value to Yes means that the user will be prompted for a location, but can dismiss the prompt.</span></span> <span data-ttu-id="69293-113">將此值設為免責聲明表示將會提示使用者輸入位置，如果使用者嘗試關閉提示，將會顯示免責聲明。</span><span class="sxs-lookup"><span data-stu-id="69293-113">Setting this value to Disclaimer means that the user will be prompted for a location, and will be shown a disclaimer if they try to dismiss the prompt.</span></span> <span data-ttu-id="69293-114">在所有情況下，使用者都可以繼續照常使用用戶端。</span><span class="sxs-lookup"><span data-stu-id="69293-114">In all cases, the user can continue to use the client as usual.</span></span>

<span data-ttu-id="69293-115">當使用者手動輸入位置時，該位置會對應至用戶端網路之預設閘道的 MAC 位址，並儲存在用戶端的每一位使用者資料表中。</span><span class="sxs-lookup"><span data-stu-id="69293-115">When a user manually enters a location, the location is mapped to the MAC address of the default gateway of the client’s network, and is stored in a per-user table located on the client.</span></span> <span data-ttu-id="69293-116">當使用者回到任何先前儲存的位置時，Lync 用戶端會自動將自己設定到該位置。</span><span class="sxs-lookup"><span data-stu-id="69293-116">When the user returns to any previously stored location, the Lync client automatically sets itself to that location.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="69293-117">您可以只修改用戶端的目前位置，但也可以刪除儲存在本機使用者資料表中的任何位置。</span><span class="sxs-lookup"><span data-stu-id="69293-117">You can modify only the current location of your client, but you can also delete any location stored in the local user’s table.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

