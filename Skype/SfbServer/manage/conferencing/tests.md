---
title: 測試商務用 Skype Server 中的電話撥入式會議
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
ms.assetid: f4ccbfd4-6075-466f-b459-20561318803d
description: 摘要：瞭解如何在商務用 Skype Server 中測試電話撥入式會議。
ms.openlocfilehash: 214ec05c49072825e6a8744cb92db66d864e3d34
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827933"
---
# <a name="test-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="62c96-103">測試商務用 Skype Server 中的電話撥入式會議</span><span class="sxs-lookup"><span data-stu-id="62c96-103">Test dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="62c96-104">**摘要：** 瞭解如何在商務用 Skype Server 中測試電話撥入式會議。</span><span class="sxs-lookup"><span data-stu-id="62c96-104">**Summary:** Learn how to test dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="62c96-105">做為您的電話撥入式會議設定的最終驗證，您可以搜尋撥號對應表，該撥號對應表中的電話撥入式會議地區未使用任何存取號碼，且未指定電話撥入式會議區域的存取號碼。</span><span class="sxs-lookup"><span data-stu-id="62c96-105">As final verification of your dial-in conferencing configuration, you can search for dial plans that have a dial-in conferencing region that is not used by any access number and for access numbers that have not specified a dial-in conferencing region.</span></span> <span data-ttu-id="62c96-106">此外，您也應驗證電話撥入式會議設定網頁和撥入式存取號碼是否運作正常。</span><span class="sxs-lookup"><span data-stu-id="62c96-106">You should also verify that the Dial-in Conferencing Settings webpage and the dial-in access numbers work correctly.</span></span>
  
## <a name="find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a><span data-ttu-id="62c96-107">使用電話撥入式會議區域（未使用的存取號碼）尋找撥號對應表</span><span class="sxs-lookup"><span data-stu-id="62c96-107">Find dial plans with a dial-in conferencing region that is not used by an access number</span></span>

1. <span data-ttu-id="62c96-108">以 RTCUniversalServerAdmins 群組成員或 Cs-ServerAdministrator、CsAdministrator 角色成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="62c96-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="62c96-109">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="62c96-109">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="62c96-110">在命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="62c96-110">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   Get-CsDialinConferencingAccessNumber -EmptyRegion
   ```

    <span data-ttu-id="62c96-111">此 Cmdlet 會傳回所有電話撥入式會議地區未由存取號碼使用的撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="62c96-111">This cmdlet returns all of the dial plans that have a dial-in conferencing region that is not used by an access number.</span></span>
    
<span data-ttu-id="62c96-112">如需詳細資訊，請參閱 [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="62c96-112">For more information, see [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="find-access-numbers-without-assigned-regions"></a><span data-ttu-id="62c96-113">尋找未指派地區的存取號碼</span><span class="sxs-lookup"><span data-stu-id="62c96-113">Find access numbers without assigned regions</span></span>

1. <span data-ttu-id="62c96-114">以 RTCUniversalServerAdmins 群組成員或 Cs-ServerAdministrator、CsAdministrator 角色成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="62c96-114">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="62c96-115">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="62c96-115">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="62c96-116">在命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="62c96-116">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   Get-CsDialinConferencingAccessNumber -Region NULL
   ```

    <span data-ttu-id="62c96-117">此 Cmdlet 會傳回與地區無關聯的所有電話撥入式會議存取號碼。</span><span class="sxs-lookup"><span data-stu-id="62c96-117">This cmdlet returns all the dial-in conferencing access numbers that are not associated with a region.</span></span>
    
<span data-ttu-id="62c96-118">如需詳細資訊，請參閱 [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="62c96-118">For more information, see [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="test-webpage-and-access-numbers"></a><span data-ttu-id="62c96-119">測試網頁和存取號碼</span><span class="sxs-lookup"><span data-stu-id="62c96-119">Test webpage and access numbers</span></span>

<span data-ttu-id="62c96-120">若要確認電話撥入式會議設定網頁和撥入式存取號碼正確運作，您需要執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="62c96-120">To verify that the Dial-in Conferencing Settings webpage and the dial-in access numbers work correctly, you need to do the following:</span></span>
  
- <span data-ttu-id="62c96-121">登入簡單 URL，以測試 [電話撥入式會議設定] 網頁。</span><span class="sxs-lookup"><span data-stu-id="62c96-121">Test the Dial-in Conferencing Settings webpage by signing in to the simple URL.</span></span>
    
- <span data-ttu-id="62c96-p102">執行本主題稍後的指令碼，以測試特定集區的存取號碼是否正常運作。此指令碼會模擬撥打存取號碼。您需要特定集區裝載控之某個整合通訊 (UC) 用戶端的 SIP 位址和認證，才能使用此指令碼。</span><span class="sxs-lookup"><span data-stu-id="62c96-p102">Test that access numbers work correctly for a specific pool by running the script later in this topic. This script simulates calls to access numbers. You need the SIP address and credentials of one unified communications (UC) client that is hosted on the specific pool to use this script.</span></span>
    
### <a name="to-test-access-numbers-for-a-specific-pool"></a><span data-ttu-id="62c96-125">若要測試特定集區的存取號碼</span><span class="sxs-lookup"><span data-stu-id="62c96-125">To test access numbers for a specific pool</span></span>

1. <span data-ttu-id="62c96-126">以 RTCUniversalServerAdmins 群組成員或 Cs-ServerAdministrator、CsAdministrator 角色成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="62c96-126">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="62c96-127">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="62c96-127">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="62c96-128">在命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="62c96-128">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   $credentials = Get-Credential
   User name:  testuser1@contoso.com
   Password:  ********
   Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
   ```

    <span data-ttu-id="62c96-129">產生的報告會顯示「成功」或「失敗」，以及特定的診斷資訊。</span><span class="sxs-lookup"><span data-stu-id="62c96-129">The resulting report shows either Success or Failure, along with specific diagnostic information.</span></span> <span data-ttu-id="62c96-130">-Verbose 旗標提供找到多少存取號碼及相關詳細資料的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="62c96-130">The -Verbose flag provides more detailed information about how many access numbers were found and details about them.</span></span>
    
<span data-ttu-id="62c96-131">如需詳細資訊，請參閱 [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="62c96-131">For more information, see [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps).</span></span>
  

