---
title: 布建 Skype 室系統交換和 Skype 帳戶的布建
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: fa71a2da-2cc9-4ad1-8ec9-08d1c9c5247a
ms.collection: M365-voice
description: 請閱讀下列主題，以瞭解如何布建 Skype 會議室系統的 Exchange 和 Skype 帳戶。
ms.openlocfilehash: be43e732a97dc81fdd2e3a6bdb355afaff4db37d
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220913"
---
# <a name="provisioning-of-skype-room-system-exchange-and-skype-accounts"></a><span data-ttu-id="9403d-103">布建 Skype 室系統交換和 Skype 帳戶的布建</span><span class="sxs-lookup"><span data-stu-id="9403d-103">Provisioning of Skype Room System Exchange and Skype Accounts</span></span>
 
<span data-ttu-id="9403d-104">請閱讀下列主題，以瞭解如何布建 Skype 會議室系統的 Exchange 和 Skype 帳戶。</span><span class="sxs-lookup"><span data-stu-id="9403d-104">Read these topics to learn how to provision Exchange and Skype accounts for Skype Room System.</span></span> 

> [!NOTE]
> <span data-ttu-id="9403d-105">Microsoft 團隊聊天室是不同的產品，具有不同的相依性和部署程式。</span><span class="sxs-lookup"><span data-stu-id="9403d-105">Microsoft Teams Rooms is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="9403d-106">如需 Microsoft 小組聊天室的詳細資訊，請參閱 Microsoft 團隊聊天室[部署概述](room-systems-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="9403d-106">For information on Microsoft Teams Rooms, see the Microsoft Teams Rooms [deployment overview](room-systems-v2.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="9403d-107">Skype 會議室系統帳戶布建取決於您的組織所擁有的拓撲類型。</span><span class="sxs-lookup"><span data-stu-id="9403d-107">Skype Room System account provisioning depends on the type of topology your organization has.</span></span> <span data-ttu-id="9403d-108">若要瞭解 Active Directory 拓撲的詳細資訊，請參閱[商務用 Skype Server 2015 的環境需求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9403d-108">To know more about Active Directory topologies, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span></span> 
  
## <a name="provisioning-of-skype-room-system-exchange-amp-skype-for-business-accounts"></a><span data-ttu-id="9403d-109">布建 Skype 室系統 Exchange &amp; 商務用 Skype 帳戶的布建</span><span class="sxs-lookup"><span data-stu-id="9403d-109">Provisioning of Skype Room System Exchange &amp; Skype for Business Accounts</span></span>

<span data-ttu-id="9403d-110">下列主題說明如何布建及管理 Skype 室系統交換和商務用 Skype 帳戶：</span><span class="sxs-lookup"><span data-stu-id="9403d-110">The following topics describe how to provision and manage Skype Room System Exchange and Skype for Business accounts for:</span></span>
  
- <span data-ttu-id="9403d-111">單一樹系內部部署</span><span class="sxs-lookup"><span data-stu-id="9403d-111">Single forest on-premises deployments</span></span>
    
- <span data-ttu-id="9403d-112">多個樹系內部部署</span><span class="sxs-lookup"><span data-stu-id="9403d-112">Multiple forest on-premises deployments</span></span>
    
- <span data-ttu-id="9403d-113">Microsoft 365 或 Office 365</span><span class="sxs-lookup"><span data-stu-id="9403d-113">Microsoft 365 or Office 365</span></span>
    
- <span data-ttu-id="9403d-114">混合式部署</span><span class="sxs-lookup"><span data-stu-id="9403d-114">Hybrid deployments</span></span>
    
- <span data-ttu-id="9403d-115">Skype 會議室系統和商務用 Skype 同盟合作夥伴</span><span class="sxs-lookup"><span data-stu-id="9403d-115">Skype Room System and Skype for Business federated partners</span></span>
    
- <span data-ttu-id="9403d-116">管理 Skype 室系統帳戶</span><span class="sxs-lookup"><span data-stu-id="9403d-116">Manage Skype Room System accounts</span></span>
    

