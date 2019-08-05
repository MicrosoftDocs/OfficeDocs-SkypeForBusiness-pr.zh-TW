---
title: 在商務用 Skype Server 中建立新的 PIN 原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8bdf0478-fe9f-4371-93ff-db39381a25db
description: '摘要: 在商務用 Skype Server 中建立新的 PIN 原則。'
ms.openlocfilehash: aaedcbfe28cb8e64b4adf7a302eef8c0d3d08a1f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189682"
---
# <a name="create-a-new-pin-policy-in-skype-for-business-server"></a><span data-ttu-id="16a0b-103">在商務用 Skype Server 中建立新的 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="16a0b-103">Create a new PIN policy in Skype for Business Server</span></span>
 
<span data-ttu-id="16a0b-104">**摘要:** 在商務用 Skype Server 中建立新的 PIN 原則。</span><span class="sxs-lookup"><span data-stu-id="16a0b-104">**Summary:** Create a new PIN policy in Skype for Business Server.</span></span>
  
<span data-ttu-id="16a0b-105">您可以使用 [**釘選原則**] 頁面, 為使用 IP 電話連線至商務用 Skype 的使用者提供個人識別碼 (pin) 驗證。</span><span class="sxs-lookup"><span data-stu-id="16a0b-105">You can use the **PIN Policy** page to provide personal identification number (PIN) authentication to users who are connecting to Skype for Business with IP Phones.</span></span> <span data-ttu-id="16a0b-106">若要使用 PIN 驗證, 請確認已在 [Web 服務設定] 中選取 [**啟用 Pin 驗證**]。</span><span class="sxs-lookup"><span data-stu-id="16a0b-106">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span>
  
<span data-ttu-id="16a0b-107">請依照這些步驟來建立使用者層級或網站層級的 PIN 原則。</span><span class="sxs-lookup"><span data-stu-id="16a0b-107">Follow these steps to create a user-level or a site-level PIN policy.</span></span> 
  
### <a name="to-create-a-user-or-site-pin-policy"></a><span data-ttu-id="16a0b-108">建立使用者或網站 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="16a0b-108">To create a user or site PIN policy</span></span>

1.  <span data-ttu-id="16a0b-109">從屬於 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權利), 或指派給 CsServerAdministrator 或 CsAdministrator 角色, 登入您在其中部署商務用 Skype Server 的網路中的任何電腦.</span><span class="sxs-lookup"><span data-stu-id="16a0b-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="16a0b-110">開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="16a0b-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="16a0b-111">在左側導覽列中, 按一下 [**安全性**], 然後按一下 [ **PIN 規則**]。</span><span class="sxs-lookup"><span data-stu-id="16a0b-111">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="16a0b-112">在 [ **PIN 原則**] 頁面上, 按一下 [**新增**], 然後執行下列其中一項操作:</span><span class="sxs-lookup"><span data-stu-id="16a0b-112">On the **PIN Policy** page, click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="16a0b-113">若要建立使用者層級原則, 按一下 [**使用者原則**]。</span><span class="sxs-lookup"><span data-stu-id="16a0b-113">To create a user-level policy, click **User policy**.</span></span> <span data-ttu-id="16a0b-114">在 [**新 PIN 原則**] 的 [**名稱**] 中, 輸入描述原則的名稱。</span><span class="sxs-lookup"><span data-stu-id="16a0b-114">In **New PIN Policy**, in **Name**, type a name that describes the policy.</span></span>
    
   - <span data-ttu-id="16a0b-115">若要建立網站層級原則, 按一下 [**網站原則**]。</span><span class="sxs-lookup"><span data-stu-id="16a0b-115">To create a site-level policy, click **Site policy**.</span></span> <span data-ttu-id="16a0b-116">在 [**選取網站**搜尋] 欄位中, 輸入您要為其建立原則之網站的全部或部分名稱。</span><span class="sxs-lookup"><span data-stu-id="16a0b-116">In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy.</span></span> <span data-ttu-id="16a0b-117">在產生的網站清單中, 按一下您想要的網站, 然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="16a0b-117">In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
5. <span data-ttu-id="16a0b-118">在 [**描述**] 欄位中, 輸入 PIN 原則的描述。</span><span class="sxs-lookup"><span data-stu-id="16a0b-118">In the **Description** field, type a description of the PIN policy.</span></span>
    
6. <span data-ttu-id="16a0b-119">在 [**最小 pin 長度**] 欄位中, 輸入或選取您要允許的最小 PIN 長度。</span><span class="sxs-lookup"><span data-stu-id="16a0b-119">In the **Minimum PIN length** field, type or select the minimum PIN length that you want to allow.</span></span> <span data-ttu-id="16a0b-120">預設的最小長度為5位數。</span><span class="sxs-lookup"><span data-stu-id="16a0b-120">The default minimum length is five digits.</span></span>
    
7. <span data-ttu-id="16a0b-121">若要在封鎖使用者之前, 能夠指定最大的登入嘗試次數, 請選取 [**指定最大登入嘗試**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="16a0b-121">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box.</span></span> <span data-ttu-id="16a0b-122">如果您沒有選取此選項, 則會根據 PIN 長度自動判斷允許的最大嘗試次數上限。</span><span class="sxs-lookup"><span data-stu-id="16a0b-122">If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length.</span></span> <span data-ttu-id="16a0b-123">根據預設, 會自動決定最大嘗試次數。</span><span class="sxs-lookup"><span data-stu-id="16a0b-123">By default, the maximum number of attempts is automatically determined.</span></span>
    
8. <span data-ttu-id="16a0b-124">如果您已選取 [**指定最大登入嘗試**] 核取方塊, 請在 [**最大登入次數**] 中, 輸入或選取您要允許的最大登入嘗試次數。</span><span class="sxs-lookup"><span data-stu-id="16a0b-124">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
9. <span data-ttu-id="16a0b-125">若要讓 Pin 到期, 請選取 [**啟用 PIN 到期**日] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="16a0b-125">To have PINs expire, select the **Enable PIN expiration** check box.</span></span> <span data-ttu-id="16a0b-126">如果您沒有選取此選項, 針腳將永不過期。</span><span class="sxs-lookup"><span data-stu-id="16a0b-126">If you do not select this option, PINs will never expire.</span></span> <span data-ttu-id="16a0b-127">根據預設, Pin 永遠不會過期。</span><span class="sxs-lookup"><span data-stu-id="16a0b-127">By default, PINs never expire.</span></span>
    
10. <span data-ttu-id="16a0b-128">如果您已選取 [**啟用 PIN 到期**日] 核取方塊, 請在 **[PIN 到期日之後 (天數)**] 中, 輸入或選取 pin 到期前的天數。</span><span class="sxs-lookup"><span data-stu-id="16a0b-128">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
11. <span data-ttu-id="16a0b-129">在 [ **PIN 記錄計數**] 中, 輸入使用者必須建立才能重複使用 pin 的 pin 數。</span><span class="sxs-lookup"><span data-stu-id="16a0b-129">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN.</span></span> <span data-ttu-id="16a0b-130">根據預設, 使用者可以重複使用他們的 Pin。</span><span class="sxs-lookup"><span data-stu-id="16a0b-130">By default, users can reuse their PINs.</span></span>
    
12. <span data-ttu-id="16a0b-131">若要在 Pin 中允許常用位數模式 (例如 "1234" 和 "8888"), 請選取 [**允許一般模式**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="16a0b-131">To allow common patterns of digits in PINs, such as "1234" and "8888", select the **Allow common patterns** check box.</span></span> <span data-ttu-id="16a0b-132">如果您沒有選取此選項, 則只允許使用複雜的數位模式。</span><span class="sxs-lookup"><span data-stu-id="16a0b-132">If you do not select this option, only complex patterns of digits are allowed.</span></span> <span data-ttu-id="16a0b-133">根據預設, 只允許使用複雜的數位模式。</span><span class="sxs-lookup"><span data-stu-id="16a0b-133">By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="16a0b-134">我們建議您不要允許通用模式。</span><span class="sxs-lookup"><span data-stu-id="16a0b-134">We recommend that you do not allow common patterns.</span></span> 
  
13. <span data-ttu-id="16a0b-135">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="16a0b-135">Click **Commit**.</span></span>
    

