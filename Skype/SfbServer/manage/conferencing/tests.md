---
title: 在商務用 Skype Server 中測試電話撥入式會議
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f4ccbfd4-6075-466f-b459-20561318803d
description: 摘要：瞭解如何在商務用 Skype Server 中測試電話撥入式會議。
ms.openlocfilehash: 838e04d7cb6d17e98df2b6fa0dbe3f3d46a5ecad
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818464"
---
# <a name="test-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="86b7c-103">在商務用 Skype Server 中測試電話撥入式會議</span><span class="sxs-lookup"><span data-stu-id="86b7c-103">Test dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="86b7c-104">**摘要：** 瞭解如何在商務用 Skype Server 中測試電話撥入式會議。</span><span class="sxs-lookup"><span data-stu-id="86b7c-104">**Summary:** Learn how to test dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="86b7c-105">針對您的電話撥入式會議設定的最終驗證，您可以搜尋其電話撥入式會議區域不是由任何存取號碼所使用的撥號方案，以及尚未指定電話撥入式會議區域的存取號碼。</span><span class="sxs-lookup"><span data-stu-id="86b7c-105">As final verification of your dial-in conferencing configuration, you can search for dial plans that have a dial-in conferencing region that is not used by any access number and for access numbers that have not specified a dial-in conferencing region.</span></span> <span data-ttu-id="86b7c-106">您也應該確認電話撥入式會議設定網頁和撥入式存取號碼都能正常運作。</span><span class="sxs-lookup"><span data-stu-id="86b7c-106">You should also verify that the Dial-in Conferencing Settings webpage and the dial-in access numbers work correctly.</span></span>
  
## <a name="find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a><span data-ttu-id="86b7c-107">使用電話撥入式會議區域尋找不是由存取號碼使用的撥號方案</span><span class="sxs-lookup"><span data-stu-id="86b7c-107">Find dial plans with a dial-in conferencing region that is not used by an access number</span></span>

1. <span data-ttu-id="86b7c-108">以 RTCUniversalServerAdmins 群組的成員或 Cs-ServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="86b7c-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="86b7c-109">啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="86b7c-109">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="86b7c-110">在命令提示字元執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="86b7c-110">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   Get-CsDialinConferencingAccessNumber -EmptyRegion
   ```

    <span data-ttu-id="86b7c-111">這個 Cmdlet 會傳回具有電話撥入式會議區域的所有撥號方案，這些方案不是由存取號碼所使用。</span><span class="sxs-lookup"><span data-stu-id="86b7c-111">This cmdlet returns all of the dial plans that have a dial-in conferencing region that is not used by an access number.</span></span>
    
<span data-ttu-id="86b7c-112">如需詳細資訊，請參閱[CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="86b7c-112">For more information, see [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="find-access-numbers-without-assigned-regions"></a><span data-ttu-id="86b7c-113">尋找不含指派區域的存取號碼</span><span class="sxs-lookup"><span data-stu-id="86b7c-113">Find access numbers without assigned regions</span></span>

1. <span data-ttu-id="86b7c-114">以 RTCUniversalServerAdmins 群組的成員或 Cs-ServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="86b7c-114">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="86b7c-115">啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="86b7c-115">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="86b7c-116">在命令提示字元執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="86b7c-116">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   Get-CsDialinConferencingAccessNumber -Region NULL
   ```

    <span data-ttu-id="86b7c-117">這個 Cmdlet 會傳回與區域不相關的所有電話撥入式會議存取號碼。</span><span class="sxs-lookup"><span data-stu-id="86b7c-117">This cmdlet returns all the dial-in conferencing access numbers that are not associated with a region.</span></span>
    
<span data-ttu-id="86b7c-118">如需詳細資訊，請參閱[CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="86b7c-118">For more information, see [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="test-webpage-and-access-numbers"></a><span data-ttu-id="86b7c-119">測試網頁和存取號碼</span><span class="sxs-lookup"><span data-stu-id="86b7c-119">Test webpage and access numbers</span></span>

<span data-ttu-id="86b7c-120">若要確認電話撥入式會議設定網頁和撥入式存取號碼都能正常運作，您必須執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="86b7c-120">To verify that the Dial-in Conferencing Settings webpage and the dial-in access numbers work correctly, you need to do the following:</span></span>
  
- <span data-ttu-id="86b7c-121">登入簡單的 URL，測試電話撥入式會議設定網頁。</span><span class="sxs-lookup"><span data-stu-id="86b7c-121">Test the Dial-in Conferencing Settings webpage by signing in to the simple URL.</span></span>
    
- <span data-ttu-id="86b7c-122">您可以在本主題稍後執行腳本，以測試存取號碼是否能在特定的池中正常運作。</span><span class="sxs-lookup"><span data-stu-id="86b7c-122">Test that access numbers work correctly for a specific pool by running the script later in this topic.</span></span> <span data-ttu-id="86b7c-123">此腳本會類比存取號碼的通話。</span><span class="sxs-lookup"><span data-stu-id="86b7c-123">This script simulates calls to access numbers.</span></span> <span data-ttu-id="86b7c-124">您需要在特定的池中託管的單一整合通訊（UC）用戶端的 SIP 位址和認證，才能使用此腳本。</span><span class="sxs-lookup"><span data-stu-id="86b7c-124">You need the SIP address and credentials of one unified communications (UC) client that is hosted on the specific pool to use this script.</span></span>
    
### <a name="to-test-access-numbers-for-a-specific-pool"></a><span data-ttu-id="86b7c-125">測試特定資源的存取號碼</span><span class="sxs-lookup"><span data-stu-id="86b7c-125">To test access numbers for a specific pool</span></span>

1. <span data-ttu-id="86b7c-126">以 RTCUniversalServerAdmins 群組的成員或 Cs-ServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="86b7c-126">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="86b7c-127">啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="86b7c-127">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="86b7c-128">在命令提示字元執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="86b7c-128">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   $credentials = Get-Credential
   User name:  testuser1@contoso.com
   Password:  ********
   Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
   ```

    <span data-ttu-id="86b7c-129">產生的報告會顯示成功或失敗，以及特定的診斷資訊。</span><span class="sxs-lookup"><span data-stu-id="86b7c-129">The resulting report shows either Success or Failure, along with specific diagnostic information.</span></span> <span data-ttu-id="86b7c-130">-Verbose 標誌提供已找到多少個存取號碼的詳細資訊，以及它們的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="86b7c-130">The -Verbose flag provides more detailed information about how many access numbers were found and details about them.</span></span>
    
<span data-ttu-id="86b7c-131">如需詳細資訊，請參閱[測試 CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="86b7c-131">For more information, see [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps).</span></span>
  

