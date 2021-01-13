---
title: 為商務用 Skype Server 中的 E9-1-1 啟用使用者
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 用於商務用 Skype Server Enterprise Voice 中的 E9-1-1 部署的位置原則，包括要啟用的使用者以及如何支援漫遊使用者的決策。
ms.openlocfilehash: 9a2ced694357b9225555a05c10e93a1006a771b4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825743"
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server"></a><span data-ttu-id="c4189-103">為商務用 Skype Server 中的 E9-1-1 啟用使用者</span><span class="sxs-lookup"><span data-stu-id="c4189-103">Enable users for E9-1-1 in Skype for Business Server</span></span>
 
<span data-ttu-id="c4189-104">用於商務用 Skype Server Enterprise Voice 中的 E9-1-1 部署的位置原則，包括要啟用的使用者以及如何支援漫遊使用者的決策。</span><span class="sxs-lookup"><span data-stu-id="c4189-104">Decisions necessary for the location policy for an E9-1-1 deployment in Skype for Business Server Enterprise Voice, including which users to enable and how to support roaming users.</span></span>
  
<span data-ttu-id="c4189-105">在用戶端註冊期間，商務用 Skype 伺服器會使用位置原則，為已啟用企業語音的使用者設定 E9-1-1 的屬性。</span><span class="sxs-lookup"><span data-stu-id="c4189-105">During client registration, Skype for Business Server uses a location policy to configure the E9-1-1 properties for Enterprise Voice-enabled users.</span></span> <span data-ttu-id="c4189-106">此原則包含的設定會定義 E9-1-1 實作方式。</span><span class="sxs-lookup"><span data-stu-id="c4189-106">This policy contains the settings that define how E9-1-1 is implemented.</span></span> <span data-ttu-id="c4189-107">例如，位置原則包含緊急撥號字串等資訊，以及如果位置資訊服務不會自動提供某個位置，是否需要使用者手動輸入位置。</span><span class="sxs-lookup"><span data-stu-id="c4189-107">For example, the location policy contains information such as the emergency dial string, and whether or not a user is required to manually enter a location if the Location Information service does not automatically provide one.</span></span> <span data-ttu-id="c4189-108">如需完整的位置原則定義，請參閱 [規劃商務用 Skype Server 的位置原則](location-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="c4189-108">For a complete definition of a location policy, see [Plan location policies for Skype for Business Server](location-policies.md).</span></span>
  
<span data-ttu-id="c4189-109">商務用 Skype 伺服器可將位置原則指派給以子網為基礎的用戶端，或根據全域、每個網站或每位使用者原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="c4189-109">Skype for Business Server can assign a location policy to clients based on subnet, or to users based on a global, per-site, or per-user policy.</span></span> <span data-ttu-id="c4189-110">如需判斷該如何啟用使用者，請先回答下列問題。</span><span class="sxs-lookup"><span data-stu-id="c4189-110">To help decide how you will enable users, you should first answer the following questions.</span></span>
  
 <span data-ttu-id="c4189-111">**您打算啟用所有使用者，還是打算將支援範圍限定在企業的特定地理區域？**</span><span class="sxs-lookup"><span data-stu-id="c4189-111">**Do you plan to enable all users, or limit support to specific geographic areas of the enterprise?**</span></span>
  
> <span data-ttu-id="c4189-112">您可以使用通用位置原則，將某個位置指派給企業中所有的使用者。</span><span class="sxs-lookup"><span data-stu-id="c4189-112">You can assign a location to all users in your enterprise by using a global location policy.</span></span> <span data-ttu-id="c4189-113">不過，您可以將位置原則指派給商務用 Skype 伺服器網路網站，然後將子網新增至網站，您可以限制 E9-1-1 對企業內所選位置的支援，並以每個網站為基礎指定 E9-1-1 路由行為。</span><span class="sxs-lookup"><span data-stu-id="c4189-113">However, by assigning a location policy to a Skype for Business Server network site and then adding subnets to the site, you can limit E9-1-1 support to selected locations within the enterprise and specify E9-1-1 routing behavior on a per-site basis.</span></span> 
    
 <span data-ttu-id="c4189-114">**您是否打算透過使用者原則啟用個別使用者？**</span><span class="sxs-lookup"><span data-stu-id="c4189-114">**Do you plan to enable individual users through a user policy?**</span></span>
  
> <span data-ttu-id="c4189-115">如果您想自訂使用者的 E9-1-1 支援，可以直接指派位置原則給特定使用者或公共區域電話連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="c4189-115">You can assign location policies directly to specific users or common area phone contact objects if you want to customize their E9-1-1 support.</span></span>
    
 <span data-ttu-id="c4189-116">**當用戶端漫遊至網路外，或從未定義的子網路連線時，是否仍應啟用用戶端的 E9-1-1？**</span><span class="sxs-lookup"><span data-stu-id="c4189-116">**When clients roam outside the network or connect from an undefined subnet, should the clients still be enabled for E9-1-1?**</span></span>
  
> <span data-ttu-id="c4189-117">如果使用者被指派全域、網站或個別使用者的位置原則，當用戶端不在已定義的子網內，或位置資訊服務找不到任何位置時，他們就可以要求他們手動將位置輸入用戶端。</span><span class="sxs-lookup"><span data-stu-id="c4189-117">If users are assigned a global, site, or per-user location policy, they can be required to manually enter a location into the client if the client is not located within a defined subnet or no location has been found by the Location Information service.</span></span> <span data-ttu-id="c4189-118">如需詳細資訊，請參閱 [定義在商務用 Skype Server 中手動取得位置的使用者經驗](manually-acquiring-a-location.md)。</span><span class="sxs-lookup"><span data-stu-id="c4189-118">For details, see [Define the user experience for manually acquiring a location in Skype for Business Server](manually-acquiring-a-location.md).</span></span>
    

