---
title: 部署用商務用 Skype Online 電話
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: faa17eb3-7483-4984-87f2-815d981b68ae
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Phone System
description: 瞭解取得正確固件的部署步驟、如有必要更新、指派授權，以及設定線上電話商務用 Skype設定
ms.openlocfilehash: 1c607f0dd5c3a82c744f26432fe1c65f31263440
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237369"
---
# <a name="deploying-skype-for-business-online-phones"></a><span data-ttu-id="884e4-103">部署用商務用 Skype Online 電話</span><span class="sxs-lookup"><span data-stu-id="884e4-103">Deploying Skype for Business Online phones</span></span>

[!INCLUDE [sfbo-retirement](../../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="884e4-104">此為部署指南，可協助您商務用 Skype Online IP 電話。</span><span class="sxs-lookup"><span data-stu-id="884e4-104">This is deployment guide will help you deploy Skype for Business Online IP phones.</span></span>
  
<span data-ttu-id="884e4-105">在所有類型的企業中，擁有電話號碼可讓使用者撥打和接聽語音電話，這是進行商務的重要需求。</span><span class="sxs-lookup"><span data-stu-id="884e4-105">In all types of businesses, having a phone number allows users to make and get voice calls, and it is an important requirement to do business.</span></span> <span data-ttu-id="884e4-106">擁有電話號碼的使用者可以在所有裝置上撥打語音商務用 Skype IP 電話、電腦和行動裝置。</span><span class="sxs-lookup"><span data-stu-id="884e4-106">Users who have phone numbers will be able to make voice calls across all Skype for Business devices including IP phones, PCs, and mobile devices.</span></span> <span data-ttu-id="884e4-107">您可以閱讀取得適用于 商務用 Skype Online 的電話，進一商務用 Skype [IP 電話](getting-phones-for-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="884e4-107">You can learn more about Skype for Business IP phones by reading [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
  
## <a name="deployment-steps-for-ip-phones"></a><span data-ttu-id="884e4-108">IP 電話的部署步驟</span><span class="sxs-lookup"><span data-stu-id="884e4-108">Deployment steps for IP phones</span></span>

### <a name="step-1---download-the-manufacturers-administrator-guides-and-phone-manuals"></a><span data-ttu-id="884e4-109">步驟 1 - 下載製造商的系統管理員指南和電話手冊</span><span class="sxs-lookup"><span data-stu-id="884e4-109">Step 1 - Download the manufacturer's administrator guides and phone manuals</span></span>

<span data-ttu-id="884e4-110">在您開始使用之前，建議先下載手機制造商的管理指南和電話使用者手冊。</span><span class="sxs-lookup"><span data-stu-id="884e4-110">Before you get started, it's a good idea to download the phone manufacturer's administration guides and phone user manuals.</span></span>
  
- <span data-ttu-id="884e4-111">針對 Polycom 電話，請參閱 [Poly 文件庫](https://documents.polycom.com/category/voice)。</span><span class="sxs-lookup"><span data-stu-id="884e4-111">For Polycom phones, see the [Poly Documentation Library](https://documents.polycom.com/category/voice).</span></span>
    
- <span data-ttu-id="884e4-112">針對 Yealink 手機，請參閱[Yealink 商務用 Skype HD SIP 電話解決方案](http://www.yealink.com/products_top_2.html)。</span><span class="sxs-lookup"><span data-stu-id="884e4-112">For Yealink phones, see [Yealink Skype for Business HD SIP Phones Solution](http://www.yealink.com/products_top_2.html).</span></span>
    
- <span data-ttu-id="884e4-113">針對 AudioCodes 手機，請參閱 [音訊代碼資源建構管理指南](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions)。</span><span class="sxs-lookup"><span data-stu-id="884e4-113">For AudioCodes phones, see the [Audiocodes Provisioning Management Guide](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).</span></span>
    
### <a name="step-2---make-sure-youre-purchasing-or-migrating-a-skype-for-business-supported-ip-phone-and-firmware"></a><span data-ttu-id="884e4-114">步驟 2 - 確認您購買或移商務用 Skype支援的 IP 電話和固件</span><span class="sxs-lookup"><span data-stu-id="884e4-114">Step 2 - Make sure you're purchasing or migrating a Skype for Business Supported IP phone and firmware</span></span>

<span data-ttu-id="884e4-115">線上商務用 Skype支援的電話和商務用 Skype Server也相容，但情況並不一定一樣。</span><span class="sxs-lookup"><span data-stu-id="884e4-115">A Skype for Business Online supported phone and firmware is compatible for Skype for Business Server as well, but the opposite isn't always true.</span></span> <span data-ttu-id="884e4-116">若要確定您購買或置備支援的手機和固件，請參閱取得適用于 商務用 Skype [Online 的手機](getting-phones-for-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="884e4-116">To make sure you are buying or provisioning a supported phone and firmware, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
  
### <a name="step-3---checking-that-the-right-firmware-is-installed-and-update-the-firmware-if-required"></a><span data-ttu-id="884e4-117">步驟 3 - 檢查已安裝正確的固件，並在需要時更新固件</span><span class="sxs-lookup"><span data-stu-id="884e4-117">Step 3 - Checking that the right firmware is installed and update the firmware if required</span></span>

<span data-ttu-id="884e4-118">檢查手機上的固件版本。</span><span class="sxs-lookup"><span data-stu-id="884e4-118">Check the firmware version on your phones.</span></span> <span data-ttu-id="884e4-119">適用于：</span><span class="sxs-lookup"><span data-stu-id="884e4-119">For:</span></span>
  
- <span data-ttu-id="884e4-120">**Polycom VVX 手機**，請設定  >    >  **狀態平臺**  >  **應用程式**  >  **主**。</span><span class="sxs-lookup"><span data-stu-id="884e4-120">**Polycom VVX phones**, go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
    
- <span data-ttu-id="884e4-121">**Yealink 手機**，請 **前往主** 電話畫面上的狀態。</span><span class="sxs-lookup"><span data-stu-id="884e4-121">**Yealink phones**, go to **Status** on the main phone screen.</span></span>
    
- <span data-ttu-id="884e4-122">**音訊代碼手機**，**從開始畫面** 前往功能表  >  **裝置**  >  狀態固件版本。</span><span class="sxs-lookup"><span data-stu-id="884e4-122">**AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="884e4-123">若要遠端存取電話詳細資料，請參閱製造商管理指南。</span><span class="sxs-lookup"><span data-stu-id="884e4-123">For remote access to phone details, refer to manufacturer administration guides.</span></span> <span data-ttu-id="884e4-124">請參閱上述使用者指南和電話手冊的連結。</span><span class="sxs-lookup"><span data-stu-id="884e4-124">See the links above for the user guides and phone manuals.</span></span> 
  
- <span data-ttu-id="884e4-125">**Lync 電話版本 (LPE**) 手機，從開始畫面系統資訊  >  功能表功能表。</span><span class="sxs-lookup"><span data-stu-id="884e4-125">**Lync Phone Edition (LPE) phones**, go to **Menu** > **System Information** from the start screen.</span></span>
    
### <a name="step-4---device-update-considerations"></a><span data-ttu-id="884e4-126">步驟 4 - 裝置更新注意事項</span><span class="sxs-lookup"><span data-stu-id="884e4-126">Step 4 - Device Update Considerations</span></span>

> [!NOTE]
> <span data-ttu-id="884e4-127">5.5.1.X 之前的 Polycom 固件具有製造商專用裝置鎖定機制，以 商務用 Skype"電話-Lock"取代。</span><span class="sxs-lookup"><span data-stu-id="884e4-127">Polycom firmware prior to 5.5.1.X had a manufacturer-specific device-lock mechanism that is replaced with a Skype for Business implementation "Phone-Lock."</span></span> <span data-ttu-id="884e4-128">使用 "device-Lock" 保護的電話從 5.4.X.X 升級為 5.5.1.X，而使用 "電話-Lock" 不會繼承 「Device-Lock」的 PIN 碼，因為「裝置鎖定」可能會讓電話不安全。</span><span class="sxs-lookup"><span data-stu-id="884e4-128">Upgrading a phone from 5.4.X.X that was secured with "Device-Lock" to 5.5.1.X with "Phone-Lock" won't inherit the PIN code from "Device-Lock," which can leave the phone unsecured.</span></span> <span data-ttu-id="884e4-129">啟用「Device-Lock」的使用者必須啟用下列 Polycom 裝置設定檔參數，讓使用者控制升級時間 (lync.deviceUpdate.popUpSK.enabled=1) 。</span><span class="sxs-lookup"><span data-stu-id="884e4-129">Users who have activated "Device-Lock" need to enable the following Polycom Device Profile parameter to give users control of time of upgrade (lync.deviceUpdate.popUpSK.enabled=1).</span></span> 
  
<span data-ttu-id="884e4-130">固件更新是由服務商務用 Skype管理。</span><span class="sxs-lookup"><span data-stu-id="884e4-130">Firmware updates are managed by the Skype for Business Service.</span></span> <span data-ttu-id="884e4-131">每個商務用 Skype認證的手機的固件都會上傳到 商務用 Skype Update 伺服器，而且根據預設，所有手機上都會啟用裝置更新。</span><span class="sxs-lookup"><span data-stu-id="884e4-131">Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span> <span data-ttu-id="884e4-132">根據電話和投票間隔上的非啟用時間，電話會自動下載並安裝最新的認證版本。</span><span class="sxs-lookup"><span data-stu-id="884e4-132">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds.</span></span> <span data-ttu-id="884e4-133">您可以使用 [Set-CsIPPhonePolicy](/powershell/module/skype/Set-CsIPPhonePolicy) Cmdlet，將 _EnableDeviceUpdate_ 參數設定為 來停用裝置更新設定 `false` 。</span><span class="sxs-lookup"><span data-stu-id="884e4-133">You can disable the device update settings by using the [Set-CsIPPhonePolicy](/powershell/module/skype/Set-CsIPPhonePolicy) cmdlet and setting the _EnableDeviceUpdate_ parameter to `false`.</span></span>
  
![顯示部署電話的螢幕擷取畫面](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
<span data-ttu-id="884e4-135">當新的固件可供使用並準備好下載及安裝時，電話會通知使用者。</span><span class="sxs-lookup"><span data-stu-id="884e4-135">When a new firmware is available and ready for download and install, the phone will notify the user.</span></span> <span data-ttu-id="884e4-136">Polycom 電話會通知使用者，並提供使用者更新 **或延** 後 **的選項**。</span><span class="sxs-lookup"><span data-stu-id="884e4-136">Polycom phones will notify the user and provide them with an option to **Update** or **Postpone**.</span></span>
  
![顯示更新和延後選項的螢幕擷取畫面。](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
<span data-ttu-id="884e4-138">對於 Polycom 電話，您可以選取 **SwUpdate** 來更新手機上的固件。</span><span class="sxs-lookup"><span data-stu-id="884e4-138">For a Polycom phone, you can update the firmware on the phone by selecting **SwUpdate**.</span></span>
  
![顯示 SwUpdate 選項的螢幕擷取畫面](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
<span data-ttu-id="884e4-140">您也可以選擇使用合作夥伴部署系統管理固件更新。</span><span class="sxs-lookup"><span data-stu-id="884e4-140">You can also choose to manage firmware updates using a partner provisioning system.</span></span> <span data-ttu-id="884e4-141">有關合作夥伴的撥備系統管理 ，包括進位電話自訂，請參閱製造商管理指南。</span><span class="sxs-lookup"><span data-stu-id="884e4-141">For partner provisioning system management including advanced phone customization, refer to manufacturer administration guides.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="884e4-142">請確定有單一裝置更新授權 (帶內裝置更新或協力廠商) 伺服器，以避免更新迴圈。</span><span class="sxs-lookup"><span data-stu-id="884e4-142">Make sure to have a single device update authority (In-band device update or a third-party provisioning server) to avoid update loops.</span></span> 
  
### <a name="step-5---configuration-and-infrastructure-phone-settings"></a><span data-ttu-id="884e4-143">步驟 5 - 設定與基礎結構電話設定</span><span class="sxs-lookup"><span data-stu-id="884e4-143">Step 5 - Configuration and infrastructure phone settings</span></span>

<span data-ttu-id="884e4-144">您可以使用 Cmdlet 的帶內商務用 Skype設定最常用的電話選項Windows PowerShell政策。</span><span class="sxs-lookup"><span data-stu-id="884e4-144">You can set up the most commonly used phone options and policies using Skype for Business In-band management Windows PowerShell cmdlets.</span></span> <span data-ttu-id="884e4-145">請參閱 [Set-CsIPPhonePolicy，](/powershell/module/skype/Set-CsIPPhonePolicy) 瞭解這些參數和設定的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="884e4-145">See [Set-CsIPPhonePolicy](/powershell/module/skype/Set-CsIPPhonePolicy) for details of those parameters and settings.</span></span>
  
<span data-ttu-id="884e4-146">有關網路基礎結構規劃，請參閱[Skype架構](https://www.skypeoperationsframework.com/)。</span><span class="sxs-lookup"><span data-stu-id="884e4-146">For network infrastructure planning, see [Skype Operations Framework](https://www.skypeoperationsframework.com/).</span></span>
  
### <a name="step-6---preparing-for-users-to-sign-in"></a><span data-ttu-id="884e4-147">步驟 6 - 準備讓使用者進行登錄</span><span class="sxs-lookup"><span data-stu-id="884e4-147">Step 6 - Preparing for users to sign in</span></span>

<span data-ttu-id="884e4-148">若要讓使用者順利登錄線上商務用 Skype電話和撥打電話，您必須確認使用者已指派正確的授權。</span><span class="sxs-lookup"><span data-stu-id="884e4-148">To enable users to successfully sign in to a Skype for Business Online phone and make calls, you need to make sure users are assigned the correct licenses.</span></span> <span data-ttu-id="884e4-149">您至少需要指派授權電話系統通話方案。</span><span class="sxs-lookup"><span data-stu-id="884e4-149">At a minimum, you will need to assign a Phone System license and a Calling Plan.</span></span> <span data-ttu-id="884e4-150">有關其他資訊，請參閱商務用 Skype附加Microsoft Teams[授權](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)，以及指派商務用 Skype Microsoft Teams[授權](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="884e4-150">For additional information, you can see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) and [Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>
  
<span data-ttu-id="884e4-151">您可以閱讀通話和通話方案，[以電話系統通話方案](/microsoftteams/calling-plan-landing-page)</span><span class="sxs-lookup"><span data-stu-id="884e4-151">You can find out more about Calling Plans by reading [Phone System and Calling Plans](/microsoftteams/calling-plan-landing-page)</span></span>
  
- <span data-ttu-id="884e4-152">**線上使用者** 可用的登錄選項為：</span><span class="sxs-lookup"><span data-stu-id="884e4-152">**Sign-in options** that are available for Online users are:</span></span>
    
  - <span data-ttu-id="884e4-153">使用 **Polycom VVX 5XX/6XX** 電話的使用者會看到：</span><span class="sxs-lookup"><span data-stu-id="884e4-153">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![顯示 Polycom 電話登入的螢幕擷取畫面](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - <span data-ttu-id="884e4-155">使用 **Yealink T48G/T46G** 電話的使用者會看到：</span><span class="sxs-lookup"><span data-stu-id="884e4-155">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![顯示 Yealink 手機登入的螢幕擷取畫面。](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    <span data-ttu-id="884e4-157">有關製造商支援的登錄選項的詳細資訊，請參閱取得適用于 商務用 Skype [Online 的電話](getting-phones-for-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="884e4-157">For details on sign-in options supported by the manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
    
- <span data-ttu-id="884e4-158">**使用者識別碼** 使用電話的鍵盤或螢幕小鍵盤 (如果) ，使用者可以使用組織的使用者名稱和密碼來登錄電話。</span><span class="sxs-lookup"><span data-stu-id="884e4-158">**User ID** Using the phone's keypad or on-screen keyboard (if available), users can use their organization's user name and password to sign in to the phone.</span></span> <span data-ttu-id="884e4-159">例如，他們應該使用 UPN <em>格式，例如</em>  amosm@contoso.com 名稱。</span><span class="sxs-lookup"><span data-stu-id="884e4-159">For example, they should use the UPN format like <em>amosm@contoso.com</em>  for their user name.</span></span>
    
     ![顯示登入畫面的螢幕擷取畫面](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!NOTE]
    > <span data-ttu-id="884e4-161">LPE 和合作夥伴 IP 電話商務用 Skype線上版不支援 PIN 驗證。</span><span class="sxs-lookup"><span data-stu-id="884e4-161">PIN authentication isn't supported for Skype for Business Online for LPE and Partner IP phones.</span></span> 
  
- <span data-ttu-id="884e4-162">**使用電腦** 當在乙太網路上 (BToE) 安裝軟體並啟用時，使用者可以使用其應用程式上的驗證視窗登入他們的電話Windows 商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="884e4-162">**Using a PC** When Better Together over Ethernet (BToE) software is installed on user's PC and enabled, users can log in to their phones using the authentication window on their Windows Skype for Business App.</span></span> <span data-ttu-id="884e4-163">請參閱 [步驟 7 (選 ](deploying-skype-for-business-online-phones.md#BK_BTOE)) - 如果您有裝置配對，且在乙太網路上 (更好搭配使用 BToE) 其他資訊。</span><span class="sxs-lookup"><span data-stu-id="884e4-163">See [Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) for other information.</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="884e4-164">使用者必須使用組織的使用者名稱和密碼來登錄電話。</span><span class="sxs-lookup"><span data-stu-id="884e4-164">Users are required to use their organization's user name and password to sign in to the phone.</span></span> <span data-ttu-id="884e4-165">例如，他們應該使用 UPN  <em>格式，例如</em>  amosm@contoso.com 名稱。</span><span class="sxs-lookup"><span data-stu-id="884e4-165">For example, they should use the UPN format like  <em>amosm@contoso.com</em>  for their user name.</span></span>
  
     ![顯示登入畫面的螢幕擷取畫面](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- <span data-ttu-id="884e4-167">**使用 Web 登錄**：這是線上使用者使用標準網頁瀏覽器進行驗證的一種新方式。</span><span class="sxs-lookup"><span data-stu-id="884e4-167">**Using a Web Sign-in**: This is a new way for Online users to authenticate using a standard web browser.</span></span> <span data-ttu-id="884e4-168">當使用者使用瀏覽器進行登錄時，系統將會提供一組指示，以遵循這些指示。</span><span class="sxs-lookup"><span data-stu-id="884e4-168">Users will be provided with a set of instructions to follow when they use a browser to sign in.</span></span>
    
  - <span data-ttu-id="884e4-169">使用 **Polycom VVX 5XX/6XX** 電話的使用者會看到：</span><span class="sxs-lookup"><span data-stu-id="884e4-169">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![顯示 Polycom 指示的螢幕擷取畫面](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - <span data-ttu-id="884e4-171">使用 **Yealink T48G/T46G** 電話的使用者會看到：</span><span class="sxs-lookup"><span data-stu-id="884e4-171">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![顯示 Yealink 指示的螢幕擷取畫面](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    <span data-ttu-id="884e4-173">產生的程式碼將在 15 分鐘後到期。</span><span class="sxs-lookup"><span data-stu-id="884e4-173">The code that is generated will expire in 15 minutes.</span></span> <span data-ttu-id="884e4-174">到期時，使用者必須按一下 [重試或確定」，以根據電話產生新代碼。</span><span class="sxs-lookup"><span data-stu-id="884e4-174">When it expires, the user will have to click **Retry** or **OK** to generate a new code, depending on the phone.</span></span>
    
  - <span data-ttu-id="884e4-175">使用 **Polycom VVX 5XX/6XX** 電話的使用者會看到：</span><span class="sxs-lookup"><span data-stu-id="884e4-175">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![顯示已過期 Polycom 程式碼的螢幕擷取畫面](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - <span data-ttu-id="884e4-177">使用 **Yealink T48G/T46G** 電話的使用者會看到：</span><span class="sxs-lookup"><span data-stu-id="884e4-177">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![顯示過期的 Yealink 程式碼的螢幕擷取畫面](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    <span data-ttu-id="884e4-179">使用瀏覽器流覽至手機上顯示的位址，然後輸入您的商務用 Skype使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="884e4-179">Using a browser, navigate to the address displayed on the phone and enter your Skype for Business username.</span></span>
    
     ![顯示電子郵件驗證的螢幕擷取畫面](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    <span data-ttu-id="884e4-181">輸入手機上顯示的代碼。</span><span class="sxs-lookup"><span data-stu-id="884e4-181">Enter the code shown on the phone.</span></span>
    
     ![顯示登入畫面上輸入代碼的螢幕擷取畫面](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    <span data-ttu-id="884e4-183">確認網站顯示「[電話製造商名稱] 商務用 Skype **認證** 電話」，然後按一下 [**繼續**]。</span><span class="sxs-lookup"><span data-stu-id="884e4-183">Verify that the site shows "[Phone Manufacturer name] **Skype for Business Certified Phone**," and click **Continue**.</span></span>
    
     ![顯示名稱驗證的螢幕擷取畫面](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    <span data-ttu-id="884e4-185">按一下使用者的認證，或按一下 [**使用另一個帳戶：**</span><span class="sxs-lookup"><span data-stu-id="884e4-185">Click the user's credentials or click **Use another account**:</span></span>
    
     ![顯示認證選項的螢幕擷取畫面](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    <span data-ttu-id="884e4-187">顯示下列頁面時，可以安全地關閉瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="884e4-187">When the following page is displayed, it is safe to close the browser.</span></span>
    
     ![顯示確認訊息的螢幕擷取畫面](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
    > [!NOTE]
    > <span data-ttu-id="884e4-189">適用于線上商務用 Skype的 LPE 電話僅支援透過 USB 連線來登錄。</span><span class="sxs-lookup"><span data-stu-id="884e4-189">LPE phones for Skype for Business Online support sign-in through USB tethering only.</span></span> 
  
- <span data-ttu-id="884e4-190">**支援的部署** 下表顯示目前支援部署模型的支援驗證類型，包括 Exchange 整合、使用多重要素驗證的新式驗證 (MFA) ，以及 商務用 Skype Online 和內部部署。</span><span class="sxs-lookup"><span data-stu-id="884e4-190">**Supported deployments** The table below shows the supported authentication types for the currently supported deployment models including Exchange Integration, Modern authentication with Multi-factor Authentication (MFA), and Skype for Business Online and on-premises.</span></span>
    
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="884e4-191">**商務用 Skype**</span><span class="sxs-lookup"><span data-stu-id="884e4-191">**Skype for Business**</span></span> <br/> |<span data-ttu-id="884e4-192">**Exchange**</span><span class="sxs-lookup"><span data-stu-id="884e4-192">**Exchange**</span></span> <br/> |<span data-ttu-id="884e4-193">**電話 Sign-In方法**</span><span class="sxs-lookup"><span data-stu-id="884e4-193">**Phone Sign-In method**</span></span> <br/> |<span data-ttu-id="884e4-194">**商務用 Skype存取權**</span><span class="sxs-lookup"><span data-stu-id="884e4-194">**Skype for Business access**</span></span> <br/> |<span data-ttu-id="884e4-195">**Exchange已停用新式驗證和 MFA 的存取**</span><span class="sxs-lookup"><span data-stu-id="884e4-195">**Exchange Access with Modern Auth and MFA disabled**</span></span> <br/> |<span data-ttu-id="884e4-196">**Exchange已啟用新式驗證和 MFA 的 Access**</span><span class="sxs-lookup"><span data-stu-id="884e4-196">**Exchange Access with Modern Auth and MFA enabled**</span></span> <br/> |
|<span data-ttu-id="884e4-197">線上</span><span class="sxs-lookup"><span data-stu-id="884e4-197">Online</span></span>  <br/> |<span data-ttu-id="884e4-198">線上</span><span class="sxs-lookup"><span data-stu-id="884e4-198">Online</span></span>  <br/> |<span data-ttu-id="884e4-199">Web 登錄</span><span class="sxs-lookup"><span data-stu-id="884e4-199">Web Sign-in</span></span>  <br/> |<span data-ttu-id="884e4-200">是</span><span class="sxs-lookup"><span data-stu-id="884e4-200">Yes</span></span>  <br/> |<span data-ttu-id="884e4-201">是</span><span class="sxs-lookup"><span data-stu-id="884e4-201">Yes</span></span>  <br/> |<span data-ttu-id="884e4-202">是</span><span class="sxs-lookup"><span data-stu-id="884e4-202">Yes</span></span>  <br/> |
|<span data-ttu-id="884e4-203">線上</span><span class="sxs-lookup"><span data-stu-id="884e4-203">Online</span></span>  <br/> |<span data-ttu-id="884e4-204">線上</span><span class="sxs-lookup"><span data-stu-id="884e4-204">Online</span></span>  <br/> |<span data-ttu-id="884e4-205">使用者名稱/密碼</span><span class="sxs-lookup"><span data-stu-id="884e4-205">Username/Password</span></span>  <br/> |<span data-ttu-id="884e4-206">是</span><span class="sxs-lookup"><span data-stu-id="884e4-206">Yes</span></span>  <br/> |<span data-ttu-id="884e4-207">是</span><span class="sxs-lookup"><span data-stu-id="884e4-207">Yes</span></span>  <br/> |<span data-ttu-id="884e4-208">否</span><span class="sxs-lookup"><span data-stu-id="884e4-208">No</span></span>  <br/> |
|<span data-ttu-id="884e4-209">線上</span><span class="sxs-lookup"><span data-stu-id="884e4-209">Online</span></span>  <br/> |<span data-ttu-id="884e4-210">內部部署</span><span class="sxs-lookup"><span data-stu-id="884e4-210">On-premises</span></span>  <br/> |<span data-ttu-id="884e4-211">Web 登錄</span><span class="sxs-lookup"><span data-stu-id="884e4-211">Web Sign-in</span></span>  <br/> |<span data-ttu-id="884e4-212">是</span><span class="sxs-lookup"><span data-stu-id="884e4-212">Yes</span></span>  <br/> |<span data-ttu-id="884e4-213">否</span><span class="sxs-lookup"><span data-stu-id="884e4-213">No</span></span>  <br/> |<span data-ttu-id="884e4-214">否</span><span class="sxs-lookup"><span data-stu-id="884e4-214">No</span></span>  <br/> |
|<span data-ttu-id="884e4-215">線上</span><span class="sxs-lookup"><span data-stu-id="884e4-215">Online</span></span>  <br/> |<span data-ttu-id="884e4-216">內部部署</span><span class="sxs-lookup"><span data-stu-id="884e4-216">On-Premises</span></span>  <br/> |<span data-ttu-id="884e4-217">使用者名稱/密碼</span><span class="sxs-lookup"><span data-stu-id="884e4-217">Username/Password</span></span>  <br/> |<span data-ttu-id="884e4-218">是</span><span class="sxs-lookup"><span data-stu-id="884e4-218">Yes</span></span>  <br/> |<span data-ttu-id="884e4-219">是</span><span class="sxs-lookup"><span data-stu-id="884e4-219">Yes</span></span>  <br/> |<span data-ttu-id="884e4-220">否</span><span class="sxs-lookup"><span data-stu-id="884e4-220">No</span></span>  <br/> |
|<span data-ttu-id="884e4-221">內部部署</span><span class="sxs-lookup"><span data-stu-id="884e4-221">On-premises</span></span>  <br/> |<span data-ttu-id="884e4-222">線上/內部部署</span><span class="sxs-lookup"><span data-stu-id="884e4-222">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="884e4-223">PIN 驗證</span><span class="sxs-lookup"><span data-stu-id="884e4-223">PIN Authentication</span></span>  <br/> |<span data-ttu-id="884e4-224">是</span><span class="sxs-lookup"><span data-stu-id="884e4-224">Yes</span></span>  <br/> |<span data-ttu-id="884e4-225">否</span><span class="sxs-lookup"><span data-stu-id="884e4-225">No</span></span>  <br/> |<span data-ttu-id="884e4-226">否</span><span class="sxs-lookup"><span data-stu-id="884e4-226">No</span></span>  <br/> |
|<span data-ttu-id="884e4-227">內部部署</span><span class="sxs-lookup"><span data-stu-id="884e4-227">On-premises</span></span>  <br/> |<span data-ttu-id="884e4-228">線上/內部部署</span><span class="sxs-lookup"><span data-stu-id="884e4-228">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="884e4-229">使用者名稱/密碼</span><span class="sxs-lookup"><span data-stu-id="884e4-229">Username/Password</span></span>  <br/> |<span data-ttu-id="884e4-230">是</span><span class="sxs-lookup"><span data-stu-id="884e4-230">Yes</span></span>  <br/> |<span data-ttu-id="884e4-231">是</span><span class="sxs-lookup"><span data-stu-id="884e4-231">Yes</span></span>  <br/> |<span data-ttu-id="884e4-232">不適用</span><span class="sxs-lookup"><span data-stu-id="884e4-232">N/A</span></span>  <br/> |
|<span data-ttu-id="884e4-233">內部部署</span><span class="sxs-lookup"><span data-stu-id="884e4-233">On-premises</span></span>  <br/> |<span data-ttu-id="884e4-234">線上/內部部署</span><span class="sxs-lookup"><span data-stu-id="884e4-234">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="884e4-235">透過 PC 或 BTOE (登錄) </span><span class="sxs-lookup"><span data-stu-id="884e4-235">Sign-in via PC (BTOE)</span></span>  <br/> |<span data-ttu-id="884e4-236">是</span><span class="sxs-lookup"><span data-stu-id="884e4-236">Yes</span></span>  <br/> |<span data-ttu-id="884e4-237">是</span><span class="sxs-lookup"><span data-stu-id="884e4-237">Yes</span></span>  <br/> |<span data-ttu-id="884e4-238">不適用</span><span class="sxs-lookup"><span data-stu-id="884e4-238">N/A</span></span>  <br/> |
   
- <span data-ttu-id="884e4-239">**電話功能** 根據 IP 電話合作夥伴的不同，功能集可能會稍有不同。</span><span class="sxs-lookup"><span data-stu-id="884e4-239">**Phone features** The feature set may vary slightly based on the IP phone partner.</span></span> <span data-ttu-id="884e4-240">有關完整功能集，以及每個手機制造商功能詳細資訊，請參閱取得適用于 商務用 Skype [Online 的手機](getting-phones-for-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="884e4-240">For the complete feature set and for more information on the features for each phone manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
    
- <span data-ttu-id="884e4-241">**電話-Lock** 是最近商務用 Skype認證電話的一項功能，可用來保護電話。</span><span class="sxs-lookup"><span data-stu-id="884e4-241">**Phone-Lock** is a recently introduced feature in Skype for Business certified phones that is used to secure a phone.</span></span> <span data-ttu-id="884e4-242">如果已啟用，系統將會要求使用者在驗證成功時建立 PIN。</span><span class="sxs-lookup"><span data-stu-id="884e4-242">If enabled, users will be asked to create a PIN upon successful authentication.</span></span> <span data-ttu-id="884e4-243">建立之後，電話會在您定義的閒置超時到期時鎖定、使用者手動鎖定手機，或使用配對功能將手機鎖定與電腦鎖定電話同步處理。</span><span class="sxs-lookup"><span data-stu-id="884e4-243">Once created, phones will lock when the idle-timeout that you define expires, a user manually locks their phone, or they sync their phone-lock with their PC lock using Phone Pairing.</span></span> <span data-ttu-id="884e4-244">如果電話鎖定 PIN 輸入錯誤數次，電話會登出使用者，或需要系統管理員程式碼才能解除鎖定電話，但這會因電話合作夥伴而異。</span><span class="sxs-lookup"><span data-stu-id="884e4-244">If the phone-lock PIN is entered wrong several times, the phone will either sign the user out or require an administrator's code to unlock the phone, but this will vary depending on the phone partner.</span></span> <span data-ttu-id="884e4-245">使用者的 PIN 應該介於 6 到 15 位數之間。</span><span class="sxs-lookup"><span data-stu-id="884e4-245">The user's PIN should be between 6 and 15 digits.</span></span>
    
    <span data-ttu-id="884e4-246">您可以針對Phone-Lock停用 (預設為啟用的) 、變更閒置-超時，以及選擇使用者是否可以在鎖定時撥打電話，或是否使用 inband-settings。</span><span class="sxs-lookup"><span data-stu-id="884e4-246">You can disable Phone-Lock for your organization (which is enabled by default), change the idle-timeout, and choose whether users can make phone calls while they are locked or not using inband-settings.</span></span> <span data-ttu-id="884e4-247">請參閱 [Set-CsUCPhoneConfiguration，](/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps) 以進一步瞭解這些設定的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="884e4-247">See [Set-CsUCPhoneConfiguration](/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps) for more details on those settings.</span></span>
    
## <a name="step-7-optional---if-you-have-device-pairing-and-better-together-over-ethernet-btoe"></a><span data-ttu-id="884e4-248">步驟 7 (選) - 如果您有裝置配對，且在乙太網路上更 (BToE) </span><span class="sxs-lookup"><span data-stu-id="884e4-248">Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)</span></span>
<span data-ttu-id="884e4-249"><a name="BK_BTOE"> </a></span><span class="sxs-lookup"><span data-stu-id="884e4-249"><a name="BK_BTOE"> </a></span></span>

<span data-ttu-id="884e4-250">BToE 是合作夥伴 IP 電話的一種電話問題機制，可讓使用者的電話與他們的應用程式配對Windows 商務用 Skype機制。</span><span class="sxs-lookup"><span data-stu-id="884e4-250">BToE is a phone paining mechanism for Partner IP phones that pairs a user's phone with their Windows Skype for Business app.</span></span> <span data-ttu-id="884e4-251">BToE 可讓使用者：</span><span class="sxs-lookup"><span data-stu-id="884e4-251">BToE enables users to:</span></span>
  
- <span data-ttu-id="884e4-252">使用桌面應用程式或電腦商務用 Skype， (IP 電話) </span><span class="sxs-lookup"><span data-stu-id="884e4-252">Sign in to their IP phone using their Skype for Business desktop app (using a PC)</span></span>
    
- <span data-ttu-id="884e4-253">使用Phone-Lock同步處理</span><span class="sxs-lookup"><span data-stu-id="884e4-253">Synchronize Phone-Lock with PC lock</span></span>
    
- <span data-ttu-id="884e4-254">按一下以撥打</span><span class="sxs-lookup"><span data-stu-id="884e4-254">Click to call</span></span>
    
<span data-ttu-id="884e4-255">BToE 可配置為以兩種模式操作：  *自動*  (預設) 和 *手動*  。</span><span class="sxs-lookup"><span data-stu-id="884e4-255">BToE can be configured to operate in two modes:  *Auto*  (default) and *Manual*  .</span></span> <span data-ttu-id="884e4-256">您也可以針對使用帶內 (設定) /停用使用者商務用 Skype此功能。</span><span class="sxs-lookup"><span data-stu-id="884e4-256">It can also be enabled (default)/disabled for users using Skype for Business in-band settings.</span></span> <span data-ttu-id="884e4-257">在手動 *模式中* 操作時，使用者必須執行額外的步驟，以將手機與應用程式Windows配對。</span><span class="sxs-lookup"><span data-stu-id="884e4-257">When operating in *Manual*  mode, users will have to take an additional step to pair their phone with their Windows app.</span></span>
  
 <span data-ttu-id="884e4-258">**將 BToE 部署到使用者**</span><span class="sxs-lookup"><span data-stu-id="884e4-258">**To deploy BToE to users**</span></span>
  
1. <span data-ttu-id="884e4-259">連線電腦埠將電腦連接到手機。</span><span class="sxs-lookup"><span data-stu-id="884e4-259">Connect their PC to their phone using the PC port.</span></span>
    
     ![顯示電腦連接的螢幕擷取畫面](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. <span data-ttu-id="884e4-261">從下列連結從製造商網站下載並安裝最新的 BToE 軟體。</span><span class="sxs-lookup"><span data-stu-id="884e4-261">Download and install the latest BToE software from the manufacturer website from the links below.</span></span> <span data-ttu-id="884e4-262">若要獲得更好的使用者體驗，您可以使用系統管理發佈解決方案來發佈及安裝 BToE 軟體，例如 Microsoft Endpoint Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="884e4-262">For a better user experience, you can distribute and install the BToE software using an admin distribution solution such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="884e4-263">有關使用 Configuration Manager 的協助，請參閱 Configuration [Manager 中的套件和程式](/configmgr/apps/deploy-use/packages-and-programs)。</span><span class="sxs-lookup"><span data-stu-id="884e4-263">For help using Configuration Manager, See [Packages and programs in Configuration Manager](/configmgr/apps/deploy-use/packages-and-programs).</span></span>
    
   - [<span data-ttu-id="884e4-264">Polycom BToE 軟體下載網站</span><span class="sxs-lookup"><span data-stu-id="884e4-264">Polycom BToE Software Download site</span></span>](https://www.polycom.com/voice-conferencing-solutions/microsoft-phones.html)
    
   - [<span data-ttu-id="884e4-265">Yealink BToE 軟體下載</span><span class="sxs-lookup"><span data-stu-id="884e4-265">Yealink BToE Software Download</span></span>](http://www.yealink.com/products_list_10.html)
    
   - [<span data-ttu-id="884e4-266">音訊代碼 BToE 軟體下載</span><span class="sxs-lookup"><span data-stu-id="884e4-266">AudioCodes BToE Software Downloads</span></span>](https://www.audiocodes.com/solutions-products/solutions/skype-for-business-microsoft-teams/skype-for-business-online)
    
3. <span data-ttu-id="884e4-267">根據預設，BToE 的伺服器設定為 **啟用\*\*\*\*和** 自動模式。</span><span class="sxs-lookup"><span data-stu-id="884e4-267">The server setting for BToE is set to **Enabled** and **Auto mode** by default.</span></span> <span data-ttu-id="884e4-268">若要變更這些設定，請參閱 [Set-CsIPPhonePolicy](/powershell/module/skype/Set-CsIPPhonePolicy)。</span><span class="sxs-lookup"><span data-stu-id="884e4-268">To change those settings, see [Set-CsIPPhonePolicy](/powershell/module/skype/Set-CsIPPhonePolicy).</span></span>
    
> [!NOTE]
> <span data-ttu-id="884e4-269">Mac 和 VDI 平臺目前不支援 BToE。</span><span class="sxs-lookup"><span data-stu-id="884e4-269">BToE isn't currently supported on Mac and VDI platforms.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="884e4-270">相關主題</span><span class="sxs-lookup"><span data-stu-id="884e4-270">Related topics</span></span>
[<span data-ttu-id="884e4-271">取得商務用 Skype 和 Microsoft Teams 的服務電話號碼</span><span class="sxs-lookup"><span data-stu-id="884e4-271">Getting service phone numbers for Skype for Business and Microsoft Teams</span></span>](/microsoftteams/getting-service-phone-numbers)

[<span data-ttu-id="884e4-272">以下是可透過電話系統獲得的功能</span><span class="sxs-lookup"><span data-stu-id="884e4-272">Here's what you get with Phone System</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="884e4-273">音訊會議與通話方案的適用國家/地區</span><span class="sxs-lookup"><span data-stu-id="884e4-273">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
