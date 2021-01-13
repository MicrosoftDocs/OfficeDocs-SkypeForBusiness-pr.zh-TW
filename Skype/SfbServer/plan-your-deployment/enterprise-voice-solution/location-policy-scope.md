---
title: 在商務用 Skype Server 中指派位置原則範圍
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
ms.assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
description: 在商務用 Skype Server Enterprise Voice 中規劃 E9-1-1 部署的位置原則。
ms.openlocfilehash: 586aabe919ea4236dc724446da717b5f300d88e9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825523"
---
# <a name="assign-location-policy-scope-in-skype-for-business-server"></a><span data-ttu-id="7437f-103">在商務用 Skype Server 中指派位置原則範圍</span><span class="sxs-lookup"><span data-stu-id="7437f-103">Assign location policy scope in Skype for Business Server</span></span>
 
<span data-ttu-id="7437f-104">在商務用 Skype Server Enterprise Voice 中規劃 E9-1-1 部署的位置原則。</span><span class="sxs-lookup"><span data-stu-id="7437f-104">Planning location policies for an E9-1-1 deployment in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="7437f-105">與其他商務用 Skype Server 原則一樣，位置原則可以指派于多個範圍層級：全域、網站和使用者。</span><span class="sxs-lookup"><span data-stu-id="7437f-105">As with other Skype for Business Server policies, location policies can be assigned at multiple scope levels: global, site, and user.</span></span> <span data-ttu-id="7437f-106">不過，使用者層級位置原則的範圍與其他商務用 Skype Server 原則的行為方式不同。</span><span class="sxs-lookup"><span data-stu-id="7437f-106">However, the scope of user-level location policies behaves a bit differently than with other Skype for Business Server policies.</span></span> <span data-ttu-id="7437f-107">每位使用者的位置原則不僅可以套用至端點物件 (例如使用者和公共區域電話連絡人物件) ，也可以套用至商務用 Skype Server 網路網站。</span><span class="sxs-lookup"><span data-stu-id="7437f-107">Not only can per-user location policies be applied to endpoint objects (such as Users and Common Area Phone contact objects), they can also be applied to Skype for Business Server network sites.</span></span> <span data-ttu-id="7437f-108">網路網站是與地理位置相關聯之用戶端子網的群組 (但不一定是整個中央網站或分支網站) 中的所有子網。</span><span class="sxs-lookup"><span data-stu-id="7437f-108">Network sites are groupings of client subnets associated with a geographical location (but may not necessarily be all subnets in an entire central site or branch site).</span></span> <span data-ttu-id="7437f-109">任何連接至網路網站之子網的用戶端，都會自動挑選指派給該網路網站的位置原則。</span><span class="sxs-lookup"><span data-stu-id="7437f-109">Any clients connected to the subnets in a network site automatically pick up the location policy assigned to that network site.</span></span> <span data-ttu-id="7437f-110">在將使用者層級位置原則指派給使用者和網路網站時，網路網站型位置原則會覆寫任何個別使用者原則設定。</span><span class="sxs-lookup"><span data-stu-id="7437f-110">In cases where a user-level location policy is assigned both to a user and to a network site, the network site-based location policy overrides any per-user policy setting.</span></span>
  
<span data-ttu-id="7437f-111">每個網站都有指派的位置原則，且每個原則都具有指派給它的不同 PSTN 使用方式、通知 URIs 和會議 URIs 值。</span><span class="sxs-lookup"><span data-stu-id="7437f-111">Each network site has a location policy assigned to it, and each policy will have different PSTN Usages, Notification URIs, and Conference URIs values assigned to it.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7437f-112">這種特殊原則範圍行為的原因在於，當位於一個 office 網站上的集區的使用者要訪問另一個網站並必須撥打緊急電話時，就會套用適當于該網路網站的 E9-1-1 通話路由設定，不論使用者指派的集區或網站為何。</span><span class="sxs-lookup"><span data-stu-id="7437f-112">The reason for this special policy scoping behavior is so that when a user homed on a pool at one office site visits another site and has to make an emergency call, the E9-1-1 call routing settings appropriate to that network site will apply no matter what pool or site the user is assigned to.</span></span> 
  

