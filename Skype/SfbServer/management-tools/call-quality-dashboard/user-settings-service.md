---
title: '通話品質儀表板 (CQD 的使用者設定服務) '
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eafeb54a-2574-415b-b991-a0ff0470d8c3
description: 摘要：瞭解使用者設定服務，此服務是用於通話品質儀表板的存放庫 API 的一部分。 通話品質儀表板是商務用 Skype 伺服器的工具。
ms.openlocfilehash: 2b2fc9810f1eceb74974dc105263b0bdcf37ae01
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803034"
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="1216d-104">通話品質儀表板 (CQD 的使用者設定服務) </span><span class="sxs-lookup"><span data-stu-id="1216d-104">User Settings Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="1216d-105">**摘要：** 瞭解使用者設定服務，此服務是用於通話品質儀表板的存放庫 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="1216d-105">**Summary:** Learn about the User Settings Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="1216d-106">通話品質儀表板是商務用 Skype 伺服器的工具。</span><span class="sxs-lookup"><span data-stu-id="1216d-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="1216d-107">使用者設定服務是用於通話品質儀表板之存放庫 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="1216d-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-settings-service"></a><span data-ttu-id="1216d-108">使用者設定服務</span><span class="sxs-lookup"><span data-stu-id="1216d-108">User Settings Service</span></span>

<span data-ttu-id="1216d-109">使用者設定是機碼組，可讓應用程式用來儲存中繼資料，以用於不同的目的，包括自訂每個使用者的應用程式行為。</span><span class="sxs-lookup"><span data-stu-id="1216d-109">User settings are key-value pairs that applications can use to store metadata for various purposes including customization of application behaviors per-user basis.</span></span> <span data-ttu-id="1216d-110">每個使用者都會收到使用者設定的儲存體。</span><span class="sxs-lookup"><span data-stu-id="1216d-110">Each user receives a storage for user settings.</span></span> <span data-ttu-id="1216d-111">只有擁有者可以新增、修改和移除使用者設定。</span><span class="sxs-lookup"><span data-stu-id="1216d-111">Only the owners can add, modify, and remove user settings.</span></span>
  
 <span data-ttu-id="1216d-112">**通用設定**</span><span class="sxs-lookup"><span data-stu-id="1216d-112">**Global Settings**</span></span>
  
<span data-ttu-id="1216d-113">全域設定是系統使用者所擁有的使用者設定，而且所有使用者都具有唯讀的存取權。</span><span class="sxs-lookup"><span data-stu-id="1216d-113">Global settings are the user settings owned by the system user, and all users have read-only access to them.</span></span> <span data-ttu-id="1216d-114">全域設定為常數：它們是在建立存放庫期間建立，永遠不會變更。</span><span class="sxs-lookup"><span data-stu-id="1216d-114">Global settings are constants: they are created during the repository creation, and they never change.</span></span>
  
<span data-ttu-id="1216d-115">每一位使用者都可以建立具有相同金鑰的使用者設定，以覆寫全域設定。</span><span class="sxs-lookup"><span data-stu-id="1216d-115">Each user can override global settings by creating user settings with the same keys.</span></span> <span data-ttu-id="1216d-116">當應用程式要求有效的使用者設定時，API 會傳回一組通用設定與使用者設定合併，每個使用者設定會取代個別的通用設定（如果機碼相同）。</span><span class="sxs-lookup"><span data-stu-id="1216d-116">When application requests the effective user settings, the API returns a set of global settings merged with the user settings, with each user setting superseding the respective global setting if keys are the same.</span></span> <span data-ttu-id="1216d-117">API 也可以只傳回使用者設定，讓應用程式可以找出已覆寫的設定。</span><span class="sxs-lookup"><span data-stu-id="1216d-117">The API can also return just the user settings so that applications can find out which settings are overridden.</span></span> 
  
<span data-ttu-id="1216d-118">其餘的作業包含在下表中。</span><span class="sxs-lookup"><span data-stu-id="1216d-118">The REST operations are included in the following table.</span></span>

|<span data-ttu-id="1216d-119">**作業**</span><span class="sxs-lookup"><span data-stu-id="1216d-119">**Operation**</span></span>|<span data-ttu-id="1216d-120">**描述**</span><span class="sxs-lookup"><span data-stu-id="1216d-120">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="1216d-121">取得使用者設定</span><span class="sxs-lookup"><span data-stu-id="1216d-121">Get User Settings</span></span>](get-user-settings.md) <br/> |<span data-ttu-id="1216d-122">取得使用者設定會傳回指定使用者的設定清單。</span><span class="sxs-lookup"><span data-stu-id="1216d-122">Get User Settings returns a list of settings for a specified user.</span></span>  <br/> |
|[<span data-ttu-id="1216d-123">取得使用者設定</span><span class="sxs-lookup"><span data-stu-id="1216d-123">Get User Setting</span></span>](get-user-setting.md) <br/> |<span data-ttu-id="1216d-124">取得使用者設定會傳回單一使用者設定。</span><span class="sxs-lookup"><span data-stu-id="1216d-124">Get User Setting returns a single user setting.</span></span>  <br/> |
   

