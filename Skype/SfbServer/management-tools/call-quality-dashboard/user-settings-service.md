---
title: 通話品質儀表板 (CQD) 的使用者設定服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eafeb54a-2574-415b-b991-a0ff0470d8c3
description: '摘要: 瞭解使用者設定服務, 這是 [通話品質] 儀表板的 [知識庫 API] 的一部分。 [通話品質儀表板] 是商務用 Skype Server 的工具。'
ms.openlocfilehash: e5e068d66adb325900b055a19aedcfaeabf4f2bc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186847"
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="b57ab-104">通話品質儀表板 (CQD) 的使用者設定服務</span><span class="sxs-lookup"><span data-stu-id="b57ab-104">User Settings Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="b57ab-105">**摘要:** 瞭解 [使用者設定] 服務, 這是 [通話品質] 儀表板的 [知識庫 API] 的一部分。</span><span class="sxs-lookup"><span data-stu-id="b57ab-105">**Summary:** Learn about the User Settings Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="b57ab-106">[通話品質儀表板] 是商務用 Skype Server 的工具。</span><span class="sxs-lookup"><span data-stu-id="b57ab-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="b57ab-107">[使用者設定] 服務是 [通話品質] 儀表板的 [知識庫 API] 的一部分。</span><span class="sxs-lookup"><span data-stu-id="b57ab-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-settings-service"></a><span data-ttu-id="b57ab-108">使用者設定服務</span><span class="sxs-lookup"><span data-stu-id="b57ab-108">User Settings Service</span></span>

<span data-ttu-id="b57ab-109">使用者設定是一些鍵值對, 應用程式可以用來儲存中繼資料以進行各種用途, 包括自訂每個使用者的應用程式行為。</span><span class="sxs-lookup"><span data-stu-id="b57ab-109">User settings are key-value pairs that applications can use to store metadata for various purposes including customization of application behaviors per-user basis.</span></span> <span data-ttu-id="b57ab-110">每個使用者都會收到使用者設定的儲存空間。</span><span class="sxs-lookup"><span data-stu-id="b57ab-110">Each user receives a storage for user settings.</span></span> <span data-ttu-id="b57ab-111">只有擁有者可以新增、修改及移除使用者設定。</span><span class="sxs-lookup"><span data-stu-id="b57ab-111">Only the owners can add, modify, and remove user settings.</span></span>
  
 <span data-ttu-id="b57ab-112">**全域設定**</span><span class="sxs-lookup"><span data-stu-id="b57ab-112">**Global Settings**</span></span>
  
<span data-ttu-id="b57ab-113">全域設定是系統使用者所擁有的使用者設定, 且所有使用者都可以以唯讀方式存取它們。</span><span class="sxs-lookup"><span data-stu-id="b57ab-113">Global settings are the user settings owned by the system user, and all users have read-only access to them.</span></span> <span data-ttu-id="b57ab-114">全域設定是常數: 它們是在建立儲存庫期間建立的, 而且永遠不會變更。</span><span class="sxs-lookup"><span data-stu-id="b57ab-114">Global settings are constants: they are created during the repository creation, and they never change.</span></span>
  
<span data-ttu-id="b57ab-115">每個使用者都可以使用相同的索引鍵來建立使用者設定, 以覆寫全域設定。</span><span class="sxs-lookup"><span data-stu-id="b57ab-115">Each user can override global settings by creating user settings with the same keys.</span></span> <span data-ttu-id="b57ab-116">當應用程式要求有效的使用者設定時, API 會傳回一組與使用者設定合併的全域設定, 每個使用者設定都會取代各個全域設定 (如果鍵相同)。</span><span class="sxs-lookup"><span data-stu-id="b57ab-116">When application requests the effective user settings, the API returns a set of global settings merged with the user settings, with each user setting superseding the respective global setting if keys are the same.</span></span> <span data-ttu-id="b57ab-117">API 也可以只傳回使用者設定, 讓應用程式可以找出哪些設定會被重寫。</span><span class="sxs-lookup"><span data-stu-id="b57ab-117">The API can also return just the user settings so that applications can find out which settings are overridden.</span></span> 
  
<span data-ttu-id="b57ab-118">其餘的作業包括在下表中。</span><span class="sxs-lookup"><span data-stu-id="b57ab-118">The REST operations are included in the following table.</span></span>

|<span data-ttu-id="b57ab-119">**一道**</span><span class="sxs-lookup"><span data-stu-id="b57ab-119">**Operation**</span></span>|<span data-ttu-id="b57ab-120">**說明**</span><span class="sxs-lookup"><span data-stu-id="b57ab-120">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="b57ab-121">取得使用者設定</span><span class="sxs-lookup"><span data-stu-id="b57ab-121">Get User Settings</span></span>](get-user-settings.md) <br/> |<span data-ttu-id="b57ab-122">[取得使用者設定] 會傳回指定使用者的設定清單。</span><span class="sxs-lookup"><span data-stu-id="b57ab-122">Get User Settings returns a list of settings for a specified user.</span></span>  <br/> |
|[<span data-ttu-id="b57ab-123">取得使用者設定</span><span class="sxs-lookup"><span data-stu-id="b57ab-123">Get User Setting</span></span>](get-user-setting.md) <br/> |<span data-ttu-id="b57ab-124">[取得使用者] 設定會傳回單一使用者設定。</span><span class="sxs-lookup"><span data-stu-id="b57ab-124">Get User Setting returns a single user setting.</span></span>  <br/> |
   

