---
title: 為使用者啟用企業語音-內部部署
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 4598565a-c228-4265-ad03-d2aef95b31a0
description: 若要讓使用者使用電話系統（雲端 PBX），您必須先啟用企業語音，並為其指派電話號碼。 您可以使用內部部署來執行這項作業，而使用者仍會駐留在內部部署中。
ms.openlocfilehash: f02638f618b32190fafcded66550b5c3dcc52f2d
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221697"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a><span data-ttu-id="94c23-104">為使用者啟用企業語音-內部部署</span><span class="sxs-lookup"><span data-stu-id="94c23-104">Enable the users for Enterprise Voice on premises</span></span>
 
<span data-ttu-id="94c23-105">若要讓使用者使用電話系統（雲端 PBX），您必須先啟用企業語音，並為其指派電話號碼。</span><span class="sxs-lookup"><span data-stu-id="94c23-105">For a user to use Phone System (Cloud PBX), you must first enable them for Enterprise Voice and assign them a phone number.</span></span> <span data-ttu-id="94c23-106">您可以使用內部部署來執行這項作業，而使用者仍會駐留在內部部署中。</span><span class="sxs-lookup"><span data-stu-id="94c23-106">You do this using your on-premises deployment while the user is still homed in the on-premises deployment.</span></span>
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a><span data-ttu-id="94c23-107">為使用者啟用企業語音內部部署和指派電話號碼</span><span class="sxs-lookup"><span data-stu-id="94c23-107">To enable a user for Enterprise Voice on premises and assign a phone number</span></span>

1. <span data-ttu-id="94c23-108">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="94c23-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="94c23-109">使用「開始」功能表或桌面快捷方式，開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="94c23-109">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    <span data-ttu-id="94c23-110">您也可以開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="94c23-110">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="94c23-111">在左導覽列中，按一下 **[使用者]**。</span><span class="sxs-lookup"><span data-stu-id="94c23-111">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="94c23-112">在 [**搜尋使用者**] 方塊中，輸入您要啟用之使用者帳戶的顯示名稱、名字、姓氏、安全性帳戶管理員（SAM）帳戶名稱、SIP 位址或線路統一資源識別元（URI）的全部或第一部分，然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="94c23-112">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="94c23-113">在表格中，按一下您要啟用 Enterprise Voice 的商務用 Skype Online 使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="94c23-113">In the table, click the Skype for Business Online user account that you want to enable for Enterprise Voice.</span></span>
    
6. <span data-ttu-id="94c23-114">在 [**編輯**] 功能表上，按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="94c23-114">On the **Edit** menu, click **Show Details**.</span></span>
    
7. <span data-ttu-id="94c23-115">在 [**電話**語音] 下，按一下 [ **Enterprise Voice**]。</span><span class="sxs-lookup"><span data-stu-id="94c23-115">Under **Telephony**, click **Enterprise Voice**.</span></span>
    
8. <span data-ttu-id="94c23-116">按一下 [**行 URI**]，然後輸入唯一的標準化電話號碼（例如電話： + 14255550200）。</span><span class="sxs-lookup"><span data-stu-id="94c23-116">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200).</span></span> <span data-ttu-id="94c23-117">然後按一下 [**認可**]。</span><span class="sxs-lookup"><span data-stu-id="94c23-117">Then click **Commit**.</span></span>
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a><span data-ttu-id="94c23-118">讓使用者在內部部署企業語音時的特殊考慮</span><span class="sxs-lookup"><span data-stu-id="94c23-118">Special considerations when enabling users for Enterprise Voice on premises</span></span>

<span data-ttu-id="94c23-119">在某些情況下，您可能需要修改讓使用者使用 Enterprise Voice 的方式，以確保他們能夠成功撥打和接聽電話。</span><span class="sxs-lookup"><span data-stu-id="94c23-119">In some cases, you may need to modify the way you enable users for Enterprise Voice to make sure that they can successfully make and receive calls.</span></span> <span data-ttu-id="94c23-120">如果您的部署中有符合下列條件的使用者，請執行所包含的步驟，以啟用使用者的 Enterprise Voice。</span><span class="sxs-lookup"><span data-stu-id="94c23-120">If you have users in your deployment that meet the following conditions, perform the steps included to enable the user for Enterprise Voice.</span></span>
  
- <span data-ttu-id="94c23-121">如果使用者是在您的內部部署 AD 中建立，然後與商務用 skype Online 同步處理，且未啟用商務用 Skype 或 Enterprise Voice，而且沒有 LineURI 集，請針對每個受影響的使用者執行下列 Cmdlet，以 \< \> 實際值取代您環境的值：</span><span class="sxs-lookup"><span data-stu-id="94c23-121">If a user is created in your on-premises AD and then synchronized with Skype for Business Online without being enabled for Skype for Business or for Enterprise Voice and do not have a LineURI set, run the following cmdlets for each affected user, replacing the values in \< \> with actual values for your environment:</span></span>
    
  ```powershell
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- <span data-ttu-id="94c23-122">如果使用者已啟用商務用 Skype 內部部署，但尚未啟用 Enterprise Voice 或已被指派 LineURI 的使用者移至商務用 Skype Online，請為每個使用者執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="94c23-122">If a user is already enabled for Skype for Business on premises, but was not enabled for Enterprise Voice or assigned a LineURI before being moved to Skype for Business Online, run the following cmdlet for each user:</span></span>
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- <span data-ttu-id="94c23-123">如果使用者已啟用商務用 Skype 內部部署，但未啟用 Enterprise Voice，即使已指派 LineURI，也請為每個受影響的使用者執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="94c23-123">If a user is already enabled in Skype for Business on premises but not enabled for Enterprise Voice, even if already assigned a LineURI, run the following cmdlet for each affected user:</span></span>
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```


