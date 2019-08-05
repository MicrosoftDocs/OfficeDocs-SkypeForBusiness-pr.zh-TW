---
title: 在商務用 Skype Server 中修改現有的 PIN 原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 517caaee-3349-4fa6-8d86-e4da3258a445
description: '摘要: 在商務用 Skype Server 中修改現有的 PIN 原則。'
ms.openlocfilehash: 9aecd7fc48ce2893e1d8e603f7cdc369cde11ec3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191569"
---
# <a name="modify-an-existing-pin-policy-in-skype-for-business-server"></a><span data-ttu-id="90b85-103">在商務用 Skype Server 中修改現有的 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="90b85-103">Modify an existing PIN policy in Skype for Business Server</span></span>
 
<span data-ttu-id="90b85-104">**摘要:** 在商務用 Skype Server 中修改現有的 PIN 原則。</span><span class="sxs-lookup"><span data-stu-id="90b85-104">**Summary:** Modify an existing PIN policy in Skype for Business Server.</span></span>
  
<span data-ttu-id="90b85-105">您可以使用 [**釘選原則**] 索引標籤, 為使用 IP 電話連線至商務用 Skype 的使用者提供個人身分識別號碼 (PIN) 驗證。</span><span class="sxs-lookup"><span data-stu-id="90b85-105">You can use the **PIN Policy** tab to provide personal identification number (PIN) authentication to users who are connecting to Skype for Business with IP Phones.</span></span> <span data-ttu-id="90b85-106">若要使用 PIN 驗證, 請確認已在 [Web 服務設定] 中選取 [**啟用 Pin 驗證**]。</span><span class="sxs-lookup"><span data-stu-id="90b85-106">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span>
  
<span data-ttu-id="90b85-107">請依照這些步驟來修改使用者層級或網站層級的 PIN 原則。</span><span class="sxs-lookup"><span data-stu-id="90b85-107">Follow these steps to modify a user-level or a site-level PIN policy.</span></span> 
  
### <a name="to-modify-an-existing-pin-policy"></a><span data-ttu-id="90b85-108">修改現有的 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="90b85-108">To modify an existing PIN policy</span></span>

1.  <span data-ttu-id="90b85-109">從屬於 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權利), 或指派給 CsServerAdministrator 或 CsAdministrator 角色, 登入您在其中部署商務用 Skype Server 的網路中的任何電腦.</span><span class="sxs-lookup"><span data-stu-id="90b85-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="90b85-110">開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="90b85-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="90b85-111">在左側導覽列中, 按一下 [**安全性**], 然後按一下 [ **PIN 規則**]。</span><span class="sxs-lookup"><span data-stu-id="90b85-111">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="90b85-112">在 [ **PIN 原則**] 頁面上, 按一下原則, 按一下 [**編輯**], 然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="90b85-112">On the **PIN Policy** page, click a policy, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="90b85-113">在 [**編輯 Pin 原則**] 的 [**最小 pin 長度**] 中, 輸入或選取您要允許的最小 pin 長度。</span><span class="sxs-lookup"><span data-stu-id="90b85-113">In **Edit PIN Policy**, in **Minimum PIN length**, type or select the minimum PIN length that you want to allow.</span></span> <span data-ttu-id="90b85-114">預設的最小長度為5位數。</span><span class="sxs-lookup"><span data-stu-id="90b85-114">The default minimum length is five digits.</span></span>
    
6. <span data-ttu-id="90b85-115">若要在封鎖使用者之前, 能夠指定最大的登入嘗試次數, 請選取 [**指定最大登入嘗試**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="90b85-115">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box.</span></span> <span data-ttu-id="90b85-116">如果您沒有選取此選項, 則會根據 PIN 長度自動判斷允許的最大嘗試次數上限。</span><span class="sxs-lookup"><span data-stu-id="90b85-116">If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length.</span></span> <span data-ttu-id="90b85-117">根據預設, 會自動決定最大嘗試次數。</span><span class="sxs-lookup"><span data-stu-id="90b85-117">By default, the maximum number of attempts is automatically determined.</span></span>
    
7. <span data-ttu-id="90b85-118">如果您已選取 [**指定最大登入嘗試**] 核取方塊, 請在 [**最大登入次數**] 中, 輸入或選取您要允許的最大登入嘗試次數。</span><span class="sxs-lookup"><span data-stu-id="90b85-118">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
8. <span data-ttu-id="90b85-119">若要讓 Pin 到期, 請選取 [**啟用 PIN 到期**日] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="90b85-119">To have PINs expire, select the **Enable PIN expiration** check box.</span></span> <span data-ttu-id="90b85-120">如果您沒有選取此選項, 針腳將永不過期。</span><span class="sxs-lookup"><span data-stu-id="90b85-120">If you do not select this option, PINs will never expire.</span></span> <span data-ttu-id="90b85-121">根據預設, Pin 永遠不會過期。</span><span class="sxs-lookup"><span data-stu-id="90b85-121">By default, PINs never expire.</span></span>
    
9. <span data-ttu-id="90b85-122">如果您已選取 [**啟用 PIN 到期**日] 核取方塊, 請在 **[PIN 到期日之後 (天數)**] 中, 輸入或選取 pin 到期前的天數。</span><span class="sxs-lookup"><span data-stu-id="90b85-122">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
10. <span data-ttu-id="90b85-123">在 [ **PIN 記錄計數**] 中, 輸入使用者必須建立才能重複使用 pin 的 pin 數。</span><span class="sxs-lookup"><span data-stu-id="90b85-123">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN.</span></span> <span data-ttu-id="90b85-124">根據預設, 使用者可以重複使用他們的 Pin。</span><span class="sxs-lookup"><span data-stu-id="90b85-124">By default, users can reuse their PINs.</span></span>
    
11. <span data-ttu-id="90b85-125">若要在 Pin 中允許通用位數 (例如順序編號和重複的數位組), 請選取 [**允許常見模式**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="90b85-125">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box.</span></span> <span data-ttu-id="90b85-126">如果您沒有選取此選項, 則只允許使用複雜的數位模式。</span><span class="sxs-lookup"><span data-stu-id="90b85-126">If you do not select this option, only complex patterns of digits are allowed.</span></span> <span data-ttu-id="90b85-127">根據預設, 只允許使用複雜的數位模式。</span><span class="sxs-lookup"><span data-stu-id="90b85-127">By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="90b85-128">我們建議您不要允許通用模式。</span><span class="sxs-lookup"><span data-stu-id="90b85-128">We recommend that you do not allow common patterns.</span></span> 
  
12. <span data-ttu-id="90b85-129">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="90b85-129">Click **Commit**.</span></span>
    

