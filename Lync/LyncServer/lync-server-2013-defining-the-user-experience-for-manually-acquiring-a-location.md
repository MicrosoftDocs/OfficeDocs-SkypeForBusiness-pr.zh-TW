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
ms.openlocfilehash: 46b5913547ab7d5030ca40070de36b4deb1f6a89
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728323"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-the-user-experience-for-manually-acquiring-a-location-in-lync-server-2013"></a><span data-ttu-id="9073a-102">定義在 Lync Server 2013 中手動取得位置的使用者體驗</span><span class="sxs-lookup"><span data-stu-id="9073a-102">Defining the user experience for manually acquiring a location in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9073a-103">_**主題上次修改日期：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="9073a-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="9073a-104">如果用戶端位於網路以外，或未定義的子網中，使用者可以手動輸入位置。</span><span class="sxs-lookup"><span data-stu-id="9073a-104">If a client is located outside the network, or in an undefined subnet, the user can manually enter a location.</span></span> <span data-ttu-id="9073a-105">但在緊急通話期間，通話會先傳送到國家/地區 E9-1-1 緊急通話回應中心（ECRC）發送器，然後再傳送到公用安全回應點（PSAP）。</span><span class="sxs-lookup"><span data-stu-id="9073a-105">But during an emergency call, the call will first be routed to a national/regional E9-1-1 Emergency Call Response Center (ECRC) dispatcher before being routed to a Public Safety Answering Point (PSAP).</span></span> <span data-ttu-id="9073a-106">ECRC 將會 verbally 查詢位置的來電者，然後根據提供的資訊將呼叫轉寄至適當的 PSAP。</span><span class="sxs-lookup"><span data-stu-id="9073a-106">The ECRC will verbally query the caller for a location and then forward the call to the appropriate PSAP, based on the information provided.</span></span>

  - <span data-ttu-id="9073a-107">**如果使用者不是由位置資訊服務自動提供某個位置，系統會提示使用者輸入位置嗎？**</span><span class="sxs-lookup"><span data-stu-id="9073a-107">**Should users be prompted to enter a location when one is not automatically provided by the Location Information service?**</span></span>  
    <span data-ttu-id="9073a-108">例如，如果用戶端位於未定義的子網、在旅館中，或在網路以外的任何地方，使用者是否必須輸入位置？</span><span class="sxs-lookup"><span data-stu-id="9073a-108">For example, if a client is located in an undefined subnet, at home, in a hotel, or anywhere else outside the network, should the user be required to enter a location?</span></span>
    
    <span data-ttu-id="9073a-109">您可以設定位置原則中**所需的位置**設定，以定義用戶端行為。</span><span class="sxs-lookup"><span data-stu-id="9073a-109">You can configure the **Location Required** setting in the location policy to define the client behavior.</span></span> <span data-ttu-id="9073a-110">將此值設定為 [否] 表示系統不會提示使用者輸入位置。</span><span class="sxs-lookup"><span data-stu-id="9073a-110">Setting this value to No means that the user will not be prompted for a location.</span></span> <span data-ttu-id="9073a-111">將此值設定為 [是] 表示系統會提示使用者輸入位置，但可以關閉提示。</span><span class="sxs-lookup"><span data-stu-id="9073a-111">Setting this value to Yes means that the user will be prompted for a location, but can dismiss the prompt.</span></span> <span data-ttu-id="9073a-112">將此值設定為 [免責聲明] 表示系統會提示使用者輸入位置，且在他們嘗試關閉提示時，會顯示免責聲明。</span><span class="sxs-lookup"><span data-stu-id="9073a-112">Setting this value to Disclaimer means that the user will be prompted for a location, and will be shown a disclaimer if they try to dismiss the prompt.</span></span> <span data-ttu-id="9073a-113">在任何情況下，使用者都可以照常繼續使用用戶端。</span><span class="sxs-lookup"><span data-stu-id="9073a-113">In all cases, the user can continue to use the client as usual.</span></span>

<span data-ttu-id="9073a-114">當使用者手動輸入位置時，該位置會對應到用戶端網路預設閘道的 MAC 位址，並儲存在用戶端的每個使用者資料表中。</span><span class="sxs-lookup"><span data-stu-id="9073a-114">When a user manually enters a location, the location is mapped to the MAC address of the default gateway of the client’s network, and is stored in a per-user table located on the client.</span></span> <span data-ttu-id="9073a-115">當使用者回到任何先前儲存的位置時，Lync 用戶端會自動將自己設為該位置。</span><span class="sxs-lookup"><span data-stu-id="9073a-115">When the user returns to any previously stored location, the Lync client automatically sets itself to that location.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="9073a-116">您只能修改用戶端的目前位置，但您也可以刪除儲存在本機使用者資料表中的任何位置。</span><span class="sxs-lookup"><span data-stu-id="9073a-116">You can modify only the current location of your client, but you can also delete any location stored in the local user’s table.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

