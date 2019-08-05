---
title: 在商務用 Skype Server 中設定會議加入頁面
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: '摘要: 瞭解如何在商務用 Skype Server 中設定 [會議加入] 頁面。'
ms.openlocfilehash: 30e220f2a1745aea0a77e3ec3ff491b842a2b221
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189646"
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server"></a><span data-ttu-id="2640b-103">在商務用 Skype Server 中設定會議加入頁面</span><span class="sxs-lookup"><span data-stu-id="2640b-103">Configure the meeting join page in Skype for Business Server</span></span>
 
<span data-ttu-id="2640b-104">**摘要:** 瞭解如何在商務用 Skype Server 中設定 [會議加入] 頁面。</span><span class="sxs-lookup"><span data-stu-id="2640b-104">**Summary:** Learn how to configure the meeting join page in Skype for Business Server.</span></span>
  
<span data-ttu-id="2640b-105">當使用者按一下會議邀請中的會議連結時, [會議加入] 頁面會偵測到使用者電腦上是否已安裝商務用 Skype 用戶端。</span><span class="sxs-lookup"><span data-stu-id="2640b-105">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Skype for Business client is already installed on the user's computer.</span></span> <span data-ttu-id="2640b-106">如果已安裝用戶端, 用戶端會開啟並加入會議。</span><span class="sxs-lookup"><span data-stu-id="2640b-106">If a client is already installed, the client opens and joins the meeting.</span></span> <span data-ttu-id="2640b-107">如果沒有安裝用戶端, 則預設會開啟商務用 Skype 用戶端。</span><span class="sxs-lookup"><span data-stu-id="2640b-107">If a client is not installed, by default the Skype for Business client opens.</span></span> 
  
## <a name="configure-the-meeting-join-page"></a><span data-ttu-id="2640b-108">設定會議加入頁面</span><span class="sxs-lookup"><span data-stu-id="2640b-108">Configure the meeting join page</span></span>

<span data-ttu-id="2640b-109">如果您想要允許使用者加入與其他用戶端版本的會議, 您可以修改會議加入頁面的行為。</span><span class="sxs-lookup"><span data-stu-id="2640b-109">You can modify the behavior of the meeting join page if you want to allow users to join meetings with other versions of the client.</span></span> <span data-ttu-id="2640b-110">這些設定選項已從商務用 Skype Server 控制台中移除, 但您可以使用 CsWebServiceConfiguration Cmdlet 進行設定。</span><span class="sxs-lookup"><span data-stu-id="2640b-110">These configuration options have been removed from the Skype for Business Server Control Panel, but you configure them by using the Set-CsWebServiceConfiguration cmdlet.</span></span>
  
<span data-ttu-id="2640b-111">**會議加入頁面集-CsWebServiceConfiguration 參數**</span><span class="sxs-lookup"><span data-stu-id="2640b-111">**Meeting Join Page Set-CsWebServiceConfiguration parameters**</span></span>

|<span data-ttu-id="2640b-112">**CsWebServiceConfiguration 參數**</span><span class="sxs-lookup"><span data-stu-id="2640b-112">**Set-CsWebServiceConfiguration parameter**</span></span>|<span data-ttu-id="2640b-113">**說明**</span><span class="sxs-lookup"><span data-stu-id="2640b-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2640b-114">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="2640b-114">ShowJoinUsingLegacyClientLink</span></span>  <br/> |<span data-ttu-id="2640b-115">此參數已棄用, 可與商務用 Skype Server 的內部部署版本搭配使用。</span><span class="sxs-lookup"><span data-stu-id="2640b-115">This parameter has been deprecated for use with the on-premises version of Skype for Business Server.</span></span>  <br/> <span data-ttu-id="2640b-116">如果設為 True, 則使用者使用商務用 Skype 以外的用戶端應用程式加入會議時, 系統會提供機會, 以使用目前的用戶端應用程式加入會議。</span><span class="sxs-lookup"><span data-stu-id="2640b-116">If set to True, users joining a meeting by using a client application other than Skype for Business will be given the opportunity to join the meeting by using their current client application.</span></span> <span data-ttu-id="2640b-117">預設值為 False。</span><span class="sxs-lookup"><span data-stu-id="2640b-117">The default value is False.</span></span>  <br/> |
|<span data-ttu-id="2640b-118">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="2640b-118">ShowAlternateJoinOptionsExpanded</span></span>  <br/> |<span data-ttu-id="2640b-119">此參數已棄用, 可與商務用 Skype Server 的內部部署版本搭配使用。</span><span class="sxs-lookup"><span data-stu-id="2640b-119">This parameter has been deprecated for use with the on-premises version of Skype for Business Server.</span></span>  <br/>  <span data-ttu-id="2640b-120">如果設為 True, 則加入線上會議的替代選項會自動展開並向使用者顯示。</span><span class="sxs-lookup"><span data-stu-id="2640b-120">If set to True, alternate options for joining an online conference are automatically expanded and shown to users.</span></span> <span data-ttu-id="2640b-121">如果設定為 False (預設值), 則可以使用這些選項, 但使用者將必須針對自己顯示選項清單。</span><span class="sxs-lookup"><span data-stu-id="2640b-121">If set to False (the default value), these options will be available, but the user will have to display the list of options for themselves.</span></span>  <br/> |
   

