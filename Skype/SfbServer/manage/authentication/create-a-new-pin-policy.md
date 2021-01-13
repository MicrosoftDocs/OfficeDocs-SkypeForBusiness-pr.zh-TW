---
title: 在商務用 Skype Server 中建立新的 PIN 原則
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
ms.assetid: 8bdf0478-fe9f-4371-93ff-db39381a25db
description: 摘要：在商務用 Skype Server 中建立新的 PIN 原則。
ms.openlocfilehash: b0d1be74e509fbaddfc59250f4f5ce05a2021260
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828403"
---
# <a name="create-a-new-pin-policy-in-skype-for-business-server"></a><span data-ttu-id="8d8ca-103">在商務用 Skype Server 中建立新的 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="8d8ca-103">Create a new PIN policy in Skype for Business Server</span></span>
 
<span data-ttu-id="8d8ca-104">**摘要：** 在商務用 Skype Server 中建立新的 PIN 原則。</span><span class="sxs-lookup"><span data-stu-id="8d8ca-104">**Summary:** Create a new PIN policy in Skype for Business Server.</span></span>
  
<span data-ttu-id="8d8ca-105">您可以使用 [ **PIN 原則** ] 頁面提供個人識別碼 (PIN) 驗證，以供使用 IP 電話連線至商務用 Skype 的使用者使用。</span><span class="sxs-lookup"><span data-stu-id="8d8ca-105">You can use the **PIN Policy** page to provide personal identification number (PIN) authentication to users who are connecting to Skype for Business with IP Phones.</span></span> <span data-ttu-id="8d8ca-106">若要使用 PIN 驗證，請確定已在 Web 服務設定中選取了 [啟用 PIN 驗證]。</span><span class="sxs-lookup"><span data-stu-id="8d8ca-106">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span>
  
<span data-ttu-id="8d8ca-107">請遵循下列步驟建立使用者層級或網站層級的 PIN 原則。</span><span class="sxs-lookup"><span data-stu-id="8d8ca-107">Follow these steps to create a user-level or a site-level PIN policy.</span></span> 
  
### <a name="to-create-a-user-or-site-pin-policy"></a><span data-ttu-id="8d8ca-108">建立使用者或網站 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="8d8ca-108">To create a user or site PIN policy</span></span>

1.  <span data-ttu-id="8d8ca-109">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您部署商務用 Skype Server 之網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="8d8ca-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="8d8ca-110">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="8d8ca-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="8d8ca-111">在左導覽列中，依序按一下 [安全性] 和 [PIN 原則]。</span><span class="sxs-lookup"><span data-stu-id="8d8ca-111">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="8d8ca-112">在 [ **PIN 原則** ] 頁面上，按一下 [ **新增**]，然後執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="8d8ca-112">On the **PIN Policy** page, click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="8d8ca-113">若要建立使用者層級原則，請按一下 [ **使用者原則**]。</span><span class="sxs-lookup"><span data-stu-id="8d8ca-113">To create a user-level policy, click **User policy**.</span></span> <span data-ttu-id="8d8ca-114">在 [ **新增 PIN 原則**] 的 [ **名稱**] 中，輸入描述原則的名稱。</span><span class="sxs-lookup"><span data-stu-id="8d8ca-114">In **New PIN Policy**, in **Name**, type a name that describes the policy.</span></span>
    
   - <span data-ttu-id="8d8ca-115">若要建立網站層級原則，請按一下 [ **網站原則**]。</span><span class="sxs-lookup"><span data-stu-id="8d8ca-115">To create a site-level policy, click **Site policy**.</span></span> <span data-ttu-id="8d8ca-116">在 [ **選取網站** ] 搜尋欄位中，輸入您要建立原則的網站名稱全部或部分名稱。</span><span class="sxs-lookup"><span data-stu-id="8d8ca-116">In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy.</span></span> <span data-ttu-id="8d8ca-117">在產生的網站清單中，按一下您想要的網站，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="8d8ca-117">In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
5. <span data-ttu-id="8d8ca-118">在 [ **描述** ] 欄位中，輸入 PIN 原則的描述。</span><span class="sxs-lookup"><span data-stu-id="8d8ca-118">In the **Description** field, type a description of the PIN policy.</span></span>
    
6. <span data-ttu-id="8d8ca-119">在 [ **最小 PIN 碼長度** ] 欄位中，輸入或選取您想要允許的最小 pin 碼長度。</span><span class="sxs-lookup"><span data-stu-id="8d8ca-119">In the **Minimum PIN length** field, type or select the minimum PIN length that you want to allow.</span></span> <span data-ttu-id="8d8ca-120">預設的最小長度為五位數。</span><span class="sxs-lookup"><span data-stu-id="8d8ca-120">The default minimum length is five digits.</span></span>
    
7. <span data-ttu-id="8d8ca-p105">若要能夠指定使用者遭鎖定前可嘗試登入的次數上限，請選取 **[指定登入嘗試次數上限]** 核取方塊。若未選取此選項，則會根據 PIN 長度自動指定允許的嘗試次數上限。依預設會自動指定嘗試次數上限。</span><span class="sxs-lookup"><span data-stu-id="8d8ca-p105">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>
    
8. <span data-ttu-id="8d8ca-124">如果您選取了 **[指定登入嘗試次數上限]** 核取方塊，請在 **[登入嘗試次數上限]** 中輸入或選取您所要允許的登入嘗試次數上限。</span><span class="sxs-lookup"><span data-stu-id="8d8ca-124">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
9. <span data-ttu-id="8d8ca-p106">若要讓 PIN 有期限，請選取 **[啟用 PIN 到期]** 核取方塊。若未選取此選項，PIN 將永不過期。根據預設，PIN 永遠不會過期。</span><span class="sxs-lookup"><span data-stu-id="8d8ca-p106">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>
    
10. <span data-ttu-id="8d8ca-128">如果您選取了 **[啟用 PIN 到期]** 核取方塊，請在 **[PIN 於下列日數後到期]** 中輸入或選取 PIN 將在幾天之後到期。</span><span class="sxs-lookup"><span data-stu-id="8d8ca-128">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
11. <span data-ttu-id="8d8ca-p107">在 **[PIN 碼歷程記錄計數]** 中，輸入使用者必須在建立多少個 PIN 之後才可重複使用 PIN。根據預設，使用者可重複使用其 PIN。</span><span class="sxs-lookup"><span data-stu-id="8d8ca-p107">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>
    
12. <span data-ttu-id="8d8ca-131">若要允許 Pin 碼的一般模式，例如 "1234" 和 "8888"，請選取 [ **允許共同模式** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="8d8ca-131">To allow common patterns of digits in PINs, such as "1234" and "8888", select the **Allow common patterns** check box.</span></span> <span data-ttu-id="8d8ca-132">若未選取此選項，則只會允許複合模式的數字。</span><span class="sxs-lookup"><span data-stu-id="8d8ca-132">If you do not select this option, only complex patterns of digits are allowed.</span></span> <span data-ttu-id="8d8ca-133">依預設只會允許複合模式的數字。</span><span class="sxs-lookup"><span data-stu-id="8d8ca-133">By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8d8ca-134">建議您不要允許共同模式。</span><span class="sxs-lookup"><span data-stu-id="8d8ca-134">We recommend that you do not allow common patterns.</span></span> 
  
13. <span data-ttu-id="8d8ca-135">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="8d8ca-135">Click **Commit**.</span></span>
    

