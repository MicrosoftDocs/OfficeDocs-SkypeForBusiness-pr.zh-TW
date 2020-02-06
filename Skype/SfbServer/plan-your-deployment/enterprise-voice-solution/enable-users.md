---
title: 在商務用 Skype Server 中啟用 E9-1-1 的使用者
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
description: 在商務用 Skype Server Enterprise Voice 中，E9-1-1 部署的位置原則所需的決定，包括要啟用哪些使用者，以及如何支援漫遊使用者。
ms.openlocfilehash: 717b127a94fbac966476c681cfb7f6e81d91bde9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802953"
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server"></a><span data-ttu-id="58daa-103">在商務用 Skype Server 中啟用 E9-1-1 的使用者</span><span class="sxs-lookup"><span data-stu-id="58daa-103">Enable users for E9-1-1 in Skype for Business Server</span></span>
 
<span data-ttu-id="58daa-104">在商務用 Skype Server Enterprise Voice 中，E9-1-1 部署的位置原則所需的決定，包括要啟用哪些使用者，以及如何支援漫遊使用者。</span><span class="sxs-lookup"><span data-stu-id="58daa-104">Decisions necessary for the location policy for an E9-1-1 deployment in Skype for Business Server Enterprise Voice, including which users to enable and how to support roaming users.</span></span>
  
<span data-ttu-id="58daa-105">在用戶端註冊期間，商務用 Skype 伺服器會使用位置原則來設定企業語音使用者的 E9 屬性。</span><span class="sxs-lookup"><span data-stu-id="58daa-105">During client registration, Skype for Business Server uses a location policy to configure the E9-1-1 properties for Enterprise Voice-enabled users.</span></span> <span data-ttu-id="58daa-106">此原則包含定義如何執行 E9-1-1 的設定。</span><span class="sxs-lookup"><span data-stu-id="58daa-106">This policy contains the settings that define how E9-1-1 is implemented.</span></span> <span data-ttu-id="58daa-107">例如，位置原則包含緊急撥號字串等資訊，以及如果位置資訊服務不會自動提供某個位置，是否需要使用者手動輸入位置。</span><span class="sxs-lookup"><span data-stu-id="58daa-107">For example, the location policy contains information such as the emergency dial string, and whether or not a user is required to manually enter a location if the Location Information service does not automatically provide one.</span></span> <span data-ttu-id="58daa-108">如需位置原則的完整定義，請參閱[規劃商務用 Skype Server 的位置原則](location-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="58daa-108">For a complete definition of a location policy, see [Plan location policies for Skype for Business Server](location-policies.md).</span></span>
  
<span data-ttu-id="58daa-109">商務用 Skype 伺服器可將位置原則指派給基於子網的客戶，或是根據全域、每個網站或每個使用者的原則來指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="58daa-109">Skype for Business Server can assign a location policy to clients based on subnet, or to users based on a global, per-site, or per-user policy.</span></span> <span data-ttu-id="58daa-110">若要協助您決定將如何啟用使用者，您應該先回答下列問題。</span><span class="sxs-lookup"><span data-stu-id="58daa-110">To help decide how you will enable users, you should first answer the following questions.</span></span>
  
 <span data-ttu-id="58daa-111">**您是否計畫要啟用所有使用者，或限制對企業特定地理區域的支援？**</span><span class="sxs-lookup"><span data-stu-id="58daa-111">**Do you plan to enable all users, or limit support to specific geographic areas of the enterprise?**</span></span>
  
> <span data-ttu-id="58daa-112">您可以使用全域位置原則，將位置指派給企業中的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="58daa-112">You can assign a location to all users in your enterprise by using a global location policy.</span></span> <span data-ttu-id="58daa-113">不過，您可以將位置原則指派給商務用 Skype Server network 網站，然後將子網新增至網站，您可以將 E9-1-1 支援限制在企業內所選的位置，並在每個網站上指定 E9 的路由行為。</span><span class="sxs-lookup"><span data-stu-id="58daa-113">However, by assigning a location policy to a Skype for Business Server network site and then adding subnets to the site, you can limit E9-1-1 support to selected locations within the enterprise and specify E9-1-1 routing behavior on a per-site basis.</span></span> 
    
 <span data-ttu-id="58daa-114">**您是否計畫透過使用者原則啟用個別使用者？**</span><span class="sxs-lookup"><span data-stu-id="58daa-114">**Do you plan to enable individual users through a user policy?**</span></span>
  
> <span data-ttu-id="58daa-115">如果您想要自訂 E9-1-1 支援，您可以將位置原則直接指派給特定的使用者或常見的區域電話連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="58daa-115">You can assign location policies directly to specific users or common area phone contact objects if you want to customize their E9-1-1 support.</span></span>
    
 <span data-ttu-id="58daa-116">**當用戶端在網路外部漫遊或從未定義的子網進行連線時，如果用戶端仍在 E9-1-1，就應該啟用用戶端嗎？**</span><span class="sxs-lookup"><span data-stu-id="58daa-116">**When clients roam outside the network or connect from an undefined subnet, should the clients still be enabled for E9-1-1?**</span></span>
  
> <span data-ttu-id="58daa-117">如果將使用者指派為全域、網站或每位使用者的位置原則，當用戶端不在已定義的子網中，或位置資訊服務找不到任何位置時，可能需要他們手動在用戶端中輸入位置。</span><span class="sxs-lookup"><span data-stu-id="58daa-117">If users are assigned a global, site, or per-user location policy, they can be required to manually enter a location into the client if the client is not located within a defined subnet or no location has been found by the Location Information service.</span></span> <span data-ttu-id="58daa-118">如需詳細資訊，請參閱[定義在商務用 Skype Server 中手動取得位置的使用者體驗](manually-acquiring-a-location.md)。</span><span class="sxs-lookup"><span data-stu-id="58daa-118">For details, see [Define the user experience for manually acquiring a location in Skype for Business Server](manually-acquiring-a-location.md).</span></span>
    

