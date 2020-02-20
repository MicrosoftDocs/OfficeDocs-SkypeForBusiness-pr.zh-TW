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
description: 瞭解如何取得正確的固件、根據需要進行更新、指派授權，以及設定商務用 Skype online 手機的設定等部署步驟
ms.openlocfilehash: f4f1a36e5a2e98c4566a81b41bc6e6c281ac9a3b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42113146"
---
# <a name="deploying-skype-for-business-online-phones"></a><span data-ttu-id="baa5c-103">部署用商務用 Skype Online 電話</span><span class="sxs-lookup"><span data-stu-id="baa5c-103">Deploying Skype for Business Online phones</span></span>

<span data-ttu-id="baa5c-104">這是部署指南，可協助您部署商務用 Skype Online IP 電話。</span><span class="sxs-lookup"><span data-stu-id="baa5c-104">This is deployment guide will help you deploy Skype for Business Online IP phones.</span></span>
  
<span data-ttu-id="baa5c-105">在所有類型的企業中，有電話號碼可以讓使用者撥打和接聽語音通話，而且這也是執行商務作業的重要需求。</span><span class="sxs-lookup"><span data-stu-id="baa5c-105">In all types of businesses, having a phone number allows users to make and get voice calls, and it is an important requirement to do business.</span></span> <span data-ttu-id="baa5c-106">擁有電話號碼的使用者可以在所有商務用 Skype 裝置上進行語音通話，包括 IP 電話、電腦及行動裝置。</span><span class="sxs-lookup"><span data-stu-id="baa5c-106">Users who have phone numbers will be able to make voice calls across all Skype for Business devices including IP phones, PCs, and mobile devices.</span></span> <span data-ttu-id="baa5c-107">您可以閱讀[取得商務用 Skype Online 的電話](getting-phones-for-skype-for-business-online.md)，進一步瞭解商務用 skype IP 手機。</span><span class="sxs-lookup"><span data-stu-id="baa5c-107">You can learn more about Skype for Business IP phones by reading [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
  
## <a name="deployment-steps-for-ip-phones"></a><span data-ttu-id="baa5c-108">IP 電話的部署步驟</span><span class="sxs-lookup"><span data-stu-id="baa5c-108">Deployment steps for IP phones</span></span>

### <a name="step-1---download-the-manufacturers-administrator-guides-and-phone-manuals"></a><span data-ttu-id="baa5c-109">步驟 1-下載製造商的管理員指南和電話手冊</span><span class="sxs-lookup"><span data-stu-id="baa5c-109">Step 1 - Download the manufacturer's administrator guides and phone manuals</span></span>

<span data-ttu-id="baa5c-110">在您開始之前，請先下載手機制造商的管理指南和手機使用者手冊。</span><span class="sxs-lookup"><span data-stu-id="baa5c-110">Before you get started, it's a good idea to download the phone manufacturer's administration guides and phone user manuals.</span></span>
  
- <span data-ttu-id="baa5c-111">若為 Polycom 手機，請參閱[Poly 文件庫](https://documents.polycom.com/category/voice)。</span><span class="sxs-lookup"><span data-stu-id="baa5c-111">For Polycom phones, see the [Poly Documentation Library](https://documents.polycom.com/category/voice).</span></span>
    
- <span data-ttu-id="baa5c-112">針對 Yealink 手機，請參閱[Yealink 商務用 SKYPE HD SIP 手機方案](http://www.yealink.com/products_top_2.html)。</span><span class="sxs-lookup"><span data-stu-id="baa5c-112">For Yealink phones, see [Yealink Skype for Business HD SIP Phones Solution](http://www.yealink.com/products_top_2.html).</span></span>
    
- <span data-ttu-id="baa5c-113">針對 AudioCodes 手機，請參閱[AudioCodes 提供管理指南](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions)。</span><span class="sxs-lookup"><span data-stu-id="baa5c-113">For AudioCodes phones, see the [Audiocodes Provisioning Management Guide](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).</span></span>
    
### <a name="step-2---make-sure-youre-purchasing-or-migrating-a-skype-for-business-supported-ip-phone-and-firmware"></a><span data-ttu-id="baa5c-114">步驟 2-確認您正在購買或遷移商務用 Skype 支援的 IP 電話與固件</span><span class="sxs-lookup"><span data-stu-id="baa5c-114">Step 2 - Make sure you're purchasing or migrating a Skype for Business Supported IP phone and firmware</span></span>

<span data-ttu-id="baa5c-115">商務用 skype Online 支援的電話和固件與商務用 Skype Server 也是相容的，但反之並非總是如此。</span><span class="sxs-lookup"><span data-stu-id="baa5c-115">A Skype for Business Online supported phone and firmware is compatible for Skype for Business Server as well, but the opposite isn't always true.</span></span> <span data-ttu-id="baa5c-116">若要確認您要購買或提供支援的電話和固件，請參閱[取得商務用 Skype Online 的電話](getting-phones-for-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="baa5c-116">To make sure you are buying or provisioning a supported phone and firmware, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
  
### <a name="step-3---checking-that-the-right-firmware-is-installed-and-update-the-firmware-if-required"></a><span data-ttu-id="baa5c-117">步驟 3-檢查是否已安裝正確的固件，並視需要更新固件</span><span class="sxs-lookup"><span data-stu-id="baa5c-117">Step 3 - Checking that the right firmware is installed and update the firmware if required</span></span>

<span data-ttu-id="baa5c-118">檢查您手機上的固件版本。</span><span class="sxs-lookup"><span data-stu-id="baa5c-118">Check the firmware version on your phones.</span></span> <span data-ttu-id="baa5c-119">作為</span><span class="sxs-lookup"><span data-stu-id="baa5c-119">For:</span></span>
  
- <span data-ttu-id="baa5c-120">**Polycom [VVX 手機**]，移至**設定** > **狀態** > **平臺** > **應用程式** > **主要**。</span><span class="sxs-lookup"><span data-stu-id="baa5c-120">**Polycom VVX phones**, go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
    
- <span data-ttu-id="baa5c-121">**Yealink [電話**]，移至 [主要電話] 畫面上的 [**狀態**]。</span><span class="sxs-lookup"><span data-stu-id="baa5c-121">**Yealink phones**, go to **Status** on the main phone screen.</span></span>
    
- <span data-ttu-id="baa5c-122">**AudioCodes [電話**]，從 [開始] 畫面移至 [**功能表** > **裝置狀態** > **固件版本**]。</span><span class="sxs-lookup"><span data-stu-id="baa5c-122">**AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="baa5c-123">如需遠端存取電話的詳細資料，請參閱製造商管理指南。</span><span class="sxs-lookup"><span data-stu-id="baa5c-123">For remote access to phone details, refer to manufacturer administration guides.</span></span> <span data-ttu-id="baa5c-124">請參閱上方的使用者指南和電話手冊連結。</span><span class="sxs-lookup"><span data-stu-id="baa5c-124">See the links above for the user guides and phone manuals.</span></span> 
  
- <span data-ttu-id="baa5c-125">**Lync Phone Edition （lpw）電話**，移至 [開始] 畫面中的 [**功能表** > **系統資訊**]。</span><span class="sxs-lookup"><span data-stu-id="baa5c-125">**Lync Phone Edition (LPE) phones**, go to **Menu** > **System Information** from the start screen.</span></span>
    
### <a name="step-4---device-update-considerations"></a><span data-ttu-id="baa5c-126">步驟 4-裝置更新考慮</span><span class="sxs-lookup"><span data-stu-id="baa5c-126">Step 4 - Device Update Considerations</span></span>

> [!NOTE]
> <span data-ttu-id="baa5c-127">Polycom 之前，請先5.5.1 固件，然後再建立一個製造商專用的裝置鎖機制，該裝置會以商務用 Skype 實現「電話-鎖定」取代。</span><span class="sxs-lookup"><span data-stu-id="baa5c-127">Polycom firmware prior to 5.5.1.X had a manufacturer-specific device-lock mechanism that is replaced with a Skype for Business implementation "Phone-Lock."</span></span> <span data-ttu-id="baa5c-128">將使用「裝置鎖」保護的 5.4. a.x 中的手機升級為5.5.1，並不會從「裝置-鎖定」繼承 PIN 碼，這可以讓手機離開不安全。</span><span class="sxs-lookup"><span data-stu-id="baa5c-128">Upgrading a phone from 5.4.X.X that was secured with "Device-Lock" to 5.5.1.X with "Phone-Lock" won't inherit the PIN code from "Device-Lock," which can leave the phone unsecured.</span></span> <span data-ttu-id="baa5c-129">已啟用「裝置鎖定」的使用者必須啟用下列 Polycom 裝置設定檔參數，讓使用者能夠控制升級的時間（popUpSK，deviceUpdate = 1）。</span><span class="sxs-lookup"><span data-stu-id="baa5c-129">Users who have activated "Device-Lock" need to enable the following Polycom Device Profile parameter to give users control of time of upgrade (lync.deviceUpdate.popUpSK.enabled=1).</span></span> 
  
<span data-ttu-id="baa5c-130">固件更新是由商務用 Skype 服務來管理。</span><span class="sxs-lookup"><span data-stu-id="baa5c-130">Firmware updates are managed by the Skype for Business Service.</span></span> <span data-ttu-id="baa5c-131">每個商務用 Skype 認證手機的固件都會上傳到商務用 Skype 補救伺服器，且預設會在所有手機上啟用裝置更新。</span><span class="sxs-lookup"><span data-stu-id="baa5c-131">Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span> <span data-ttu-id="baa5c-132">電話會自動下載並安裝最新的認證組建，這取決於電話和巡迴檢測間隔中的非啟用時間。</span><span class="sxs-lookup"><span data-stu-id="baa5c-132">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds.</span></span> <span data-ttu-id="baa5c-133">您可以使用[CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx) Cmdlet 來停用裝置更新設定，並將_EnableDeviceUpdate_參數設定為`false`。</span><span class="sxs-lookup"><span data-stu-id="baa5c-133">You can disable the device update settings by using the [Set-CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx) cmdlet and setting the _EnableDeviceUpdate_ parameter to `false`.</span></span>
  
![顯示部署手機的螢幕擷取畫面](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
<span data-ttu-id="baa5c-135">當有新的固件可供下載和安裝時，電話會通知使用者。</span><span class="sxs-lookup"><span data-stu-id="baa5c-135">When a new firmware is available and ready for download and install, the phone will notify the user.</span></span> <span data-ttu-id="baa5c-136">Polycom [電話] 會通知使用者，並提供**更新**或**延遲**的選項。</span><span class="sxs-lookup"><span data-stu-id="baa5c-136">Polycom phones will notify the user and provide them with an option to **Update** or **Postpone**.</span></span>
  
![顯示 [更新及推遲] 選項的螢幕擷取畫面。](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
<span data-ttu-id="baa5c-138">若是 Polycom 電話，您可以選取 [ **SwUpdate**] 來更新手機上的固件。</span><span class="sxs-lookup"><span data-stu-id="baa5c-138">For a Polycom phone, you can update the firmware on the phone by selecting **SwUpdate**.</span></span>
  
![顯示 [SwUpdate] 選項的螢幕擷取畫面](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
<span data-ttu-id="baa5c-140">您也可以選擇使用合作夥伴置備系統管理固件更新。</span><span class="sxs-lookup"><span data-stu-id="baa5c-140">You can also choose to manage firmware updates using a partner provisioning system.</span></span> <span data-ttu-id="baa5c-141">如需合作夥伴置備系統管理（包括高級電話自訂），請參閱製造商管理指南。</span><span class="sxs-lookup"><span data-stu-id="baa5c-141">For partner provisioning system management including advanced phone customization, refer to manufacturer administration guides.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="baa5c-142">請務必使用單一裝置更新頒發機構（帶內裝置更新或協力廠商置備伺服器）來避免更新迴圈。</span><span class="sxs-lookup"><span data-stu-id="baa5c-142">Make sure to have a single device update authority (In-band device update or a third-party provisioning server) to avoid update loops.</span></span> 
  
### <a name="step-5---configuration-and-infrastructure-phone-settings"></a><span data-ttu-id="baa5c-143">步驟 5-配置與基礎結構電話設定</span><span class="sxs-lookup"><span data-stu-id="baa5c-143">Step 5 - Configuration and infrastructure phone settings</span></span>

<span data-ttu-id="baa5c-144">您可以使用商務用 Skype 頻帶內管理 Windows PowerShell Cmdlet 來設定最常用的電話選項和原則。</span><span class="sxs-lookup"><span data-stu-id="baa5c-144">You can set up the most commonly used phone options and policies using Skype for Business In-band management Windows PowerShell cmdlets.</span></span> <span data-ttu-id="baa5c-145">如需這些參數和設定的詳細資料，請參閱[設定 CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="baa5c-145">See [Set-CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx) for details of those parameters and settings.</span></span>
  
<span data-ttu-id="baa5c-146">如需網路基礎結構規劃，請參閱[Skype 操作架構](https://www.skypeoperationsframework.com/)。</span><span class="sxs-lookup"><span data-stu-id="baa5c-146">For network infrastructure planning, see [Skype Operations Framework](https://www.skypeoperationsframework.com/).</span></span>
  
### <a name="step-6---preparing-for-users-to-sign-in"></a><span data-ttu-id="baa5c-147">步驟 6-準備使用者以進行登入</span><span class="sxs-lookup"><span data-stu-id="baa5c-147">Step 6 - Preparing for users to sign in</span></span>

<span data-ttu-id="baa5c-148">若要讓使用者能夠成功登入商務用 Skype Online 手機並撥打電話，您必須確認已為使用者指派正確的授權。</span><span class="sxs-lookup"><span data-stu-id="baa5c-148">To enable users to successfully sign in to a Skype for Business Online phone and make calls, you need to make sure users are assigned the correct licenses.</span></span> <span data-ttu-id="baa5c-149">您必須至少指派電話系統授權和通話方案。</span><span class="sxs-lookup"><span data-stu-id="baa5c-149">At a minimum, you will need to assign a Phone System license and a Calling Plan.</span></span> <span data-ttu-id="baa5c-150">如需其他資訊，您可以查看[商務用 skype 和 Microsoft 團隊附加元件授權](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)，以及[指派商務用 Skype 和 Microsoft 團隊](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)授權。</span><span class="sxs-lookup"><span data-stu-id="baa5c-150">For additional information, you can see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) and [Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>
  
<span data-ttu-id="baa5c-151">您可以閱讀[電話系統和通話方案](/microsoftteams/calling-plan-landing-page)，以瞭解通話方案的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="baa5c-151">You can find out more about Calling Plans by reading [Phone System and Calling Plans](/microsoftteams/calling-plan-landing-page)</span></span>
  
- <span data-ttu-id="baa5c-152">可供線上使用者使用的登**入選項**包括：</span><span class="sxs-lookup"><span data-stu-id="baa5c-152">**Sign-in options** that are available for Online users are:</span></span>
    
  - <span data-ttu-id="baa5c-153">**POLYCOM VVX 5xx/6xx**手機的使用者將會看到：</span><span class="sxs-lookup"><span data-stu-id="baa5c-153">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![顯示 [Polycom 電話] 登入的螢幕擷取畫面](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - <span data-ttu-id="baa5c-155">**YEALINK T48G/T46G**手機的使用者將會看到：</span><span class="sxs-lookup"><span data-stu-id="baa5c-155">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![螢幕擷取畫面顯示 [Yealink 電話登入]。](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    <span data-ttu-id="baa5c-157">如需製造商支援的登入選項的詳細資料，請參閱[取得商務用 Skype Online 的電話](getting-phones-for-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="baa5c-157">For details on sign-in options supported by the manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
    
- <span data-ttu-id="baa5c-158">**使用者識別碼**使用電話鍵台或螢幕小鍵盤（如果有的話），使用者可以使用其組織的使用者名稱和密碼登入手機。</span><span class="sxs-lookup"><span data-stu-id="baa5c-158">**User ID** Using the phone's keypad or on-screen keyboard (if available), users can use their organization's user name and password to sign in to the phone.</span></span> <span data-ttu-id="baa5c-159">例如，他們應該使用 UPN 格式，例如<em>amosm@contoso.com</em>的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="baa5c-159">For example, they should use the UPN format like <em>amosm@contoso.com</em>  for their user name.</span></span>
    
     ![顯示 [登入] 畫面的螢幕擷取畫面](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!NOTE]
    > <span data-ttu-id="baa5c-161">LPW 和合作夥伴 IP 手機的商務用 Skype Online 不支援 PIN 驗證。</span><span class="sxs-lookup"><span data-stu-id="baa5c-161">PIN authentication isn't supported for Skype for Business Online for LPE and Partner IP phones.</span></span> 
  
- <span data-ttu-id="baa5c-162">**使用電腦**當您在使用者的電腦上安裝較高乙太網路（BToE）軟體且已啟用時，使用者可以使用 Windows 商務用 Skype App 上的驗證視窗登入他們的手機。</span><span class="sxs-lookup"><span data-stu-id="baa5c-162">**Using a PC** When Better Together over Ethernet (BToE) software is installed on user's PC and enabled, users can log in to their phones using the authentication window on their Windows Skype for Business App.</span></span> <span data-ttu-id="baa5c-163">請參閱[步驟7（選用）-如果您有裝置配對，且更好搭配乙太網路（BToE）使用](deploying-skype-for-business-online-phones.md#BK_BTOE)，以取得其他資訊。</span><span class="sxs-lookup"><span data-stu-id="baa5c-163">See [Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) for other information.</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="baa5c-164">使用者必須使用組織的使用者名稱和密碼，才能登入電話。</span><span class="sxs-lookup"><span data-stu-id="baa5c-164">Users are required to use their organization's user name and password to sign in to the phone.</span></span> <span data-ttu-id="baa5c-165">例如，他們應該使用 UPN 格式，例如<em>amosm@contoso.com</em>的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="baa5c-165">For example, they should use the UPN format like  <em>amosm@contoso.com</em>  for their user name.</span></span>
  
     ![顯示 [登入] 畫面的螢幕擷取畫面](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- <span data-ttu-id="baa5c-167">**使用 Web 登入**：這是線上使用者使用標準網頁瀏覽器進行驗證的新方法。</span><span class="sxs-lookup"><span data-stu-id="baa5c-167">**Using a Web Sign-in**: This is a new way for Online users to authenticate using a standard web browser.</span></span> <span data-ttu-id="baa5c-168">當使用者使用瀏覽器登入時，系統會提供一組指示以進行追蹤。</span><span class="sxs-lookup"><span data-stu-id="baa5c-168">Users will be provided with a set of instructions to follow when they use a browser to sign in.</span></span>
    
  - <span data-ttu-id="baa5c-169">**POLYCOM VVX 5xx/6xx**手機的使用者將會看到：</span><span class="sxs-lookup"><span data-stu-id="baa5c-169">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![螢幕擷取畫面顯示 Polycom 指示](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - <span data-ttu-id="baa5c-171">**YEALINK T48G/T46G**手機的使用者將會看到：</span><span class="sxs-lookup"><span data-stu-id="baa5c-171">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![顯示 Yealink 指示的螢幕擷取畫面](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    <span data-ttu-id="baa5c-173">產生的程式碼將在15分鐘後到期。</span><span class="sxs-lookup"><span data-stu-id="baa5c-173">The code that is generated will expire in 15 minutes.</span></span> <span data-ttu-id="baa5c-174">當它到期時，使用者必須按一下 [**重試** **] 或 [確定]** 來產生新的程式碼（視電話而定）。</span><span class="sxs-lookup"><span data-stu-id="baa5c-174">When it expires, the user will have to click **Retry** or **OK** to generate a new code, depending on the phone.</span></span>
    
  - <span data-ttu-id="baa5c-175">**POLYCOM VVX 5xx/6xx**手機的使用者將會看到：</span><span class="sxs-lookup"><span data-stu-id="baa5c-175">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![螢幕擷取畫面顯示已過期的 Polycom 程式碼](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - <span data-ttu-id="baa5c-177">**YEALINK T48G/T46G**手機的使用者將會看到：</span><span class="sxs-lookup"><span data-stu-id="baa5c-177">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![螢幕擷取畫面顯示已過期的 Yealink 程式碼](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    <span data-ttu-id="baa5c-179">使用瀏覽器流覽至手機上顯示的位址，然後輸入商務用 Skype 的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="baa5c-179">Using a browser, navigate to the address displayed on the phone and enter your Skype for Business username.</span></span>
    
     ![顯示電子郵件驗證的螢幕擷取畫面](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    <span data-ttu-id="baa5c-181">輸入在手機上顯示的程式碼。</span><span class="sxs-lookup"><span data-stu-id="baa5c-181">Enter the code shown on the phone.</span></span>
    
     ![螢幕擷取畫面顯示在登入畫面上輸入程式碼](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    <span data-ttu-id="baa5c-183">確認網站顯示「[電話製造商名稱] 商務用**Skype 認證電話**」，然後按一下 [**繼續**]。</span><span class="sxs-lookup"><span data-stu-id="baa5c-183">Verify that the site shows "[Phone Manufacturer name] **Skype for Business Certified Phone**," and click **Continue**.</span></span>
    
     ![顯示驗證名稱的螢幕擷取畫面](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    <span data-ttu-id="baa5c-185">按一下使用者的認證，或按一下 [**使用其他帳戶**]：</span><span class="sxs-lookup"><span data-stu-id="baa5c-185">Click the user's credentials or click **Use another account**:</span></span>
    
     ![顯示認證選項的螢幕擷取畫面](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    <span data-ttu-id="baa5c-187">出現下列頁面時，可以放心關閉瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="baa5c-187">When the following page is displayed, it is safe to close the browser.</span></span>
    
     ![顯示確認訊息的螢幕擷取畫面](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
    > [!NOTE]
    > <span data-ttu-id="baa5c-189">LPW 商務用 Skype Online 的手機支援僅透過 USB tethering 登入。</span><span class="sxs-lookup"><span data-stu-id="baa5c-189">LPE phones for Skype for Business Online support sign-in through USB tethering only.</span></span> 
  
- <span data-ttu-id="baa5c-190">**支援的部署**下表顯示目前支援之部署模型支援的驗證類型，包括 Exchange 整合、使用多重要素驗證（MFA）及商務用 Skype Online 與內部部署的 Skype 驗證。</span><span class="sxs-lookup"><span data-stu-id="baa5c-190">**Supported deployments** The table below shows the supported authentication types for the currently supported deployment models including Exchange Integration, Modern authentication with Multi-factor Authentication (MFA), and Skype for Business Online and on-premises.</span></span>
    
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="baa5c-191">**商務用 Skype**</span><span class="sxs-lookup"><span data-stu-id="baa5c-191">**Skype for Business**</span></span> <br/> |<span data-ttu-id="baa5c-192">**證券**</span><span class="sxs-lookup"><span data-stu-id="baa5c-192">**Exchange**</span></span> <br/> |<span data-ttu-id="baa5c-193">**電話登入方法**</span><span class="sxs-lookup"><span data-stu-id="baa5c-193">**Phone Sign-In method**</span></span> <br/> |<span data-ttu-id="baa5c-194">**商務用 Skype access**</span><span class="sxs-lookup"><span data-stu-id="baa5c-194">**Skype for Business access**</span></span> <br/> |<span data-ttu-id="baa5c-195">**已停用新式驗證與 MFA 的 Exchange 存取**</span><span class="sxs-lookup"><span data-stu-id="baa5c-195">**Exchange Access with Modern Auth and MFA disabled**</span></span> <br/> |<span data-ttu-id="baa5c-196">**已啟用新式驗證與 MFA 的 Exchange 存取**</span><span class="sxs-lookup"><span data-stu-id="baa5c-196">**Exchange Access with Modern Auth and MFA enabled**</span></span> <br/> |
|<span data-ttu-id="baa5c-197">Online</span><span class="sxs-lookup"><span data-stu-id="baa5c-197">Online</span></span>  <br/> |<span data-ttu-id="baa5c-198">Online</span><span class="sxs-lookup"><span data-stu-id="baa5c-198">Online</span></span>  <br/> |<span data-ttu-id="baa5c-199">網頁登入</span><span class="sxs-lookup"><span data-stu-id="baa5c-199">Web Sign-in</span></span>  <br/> |<span data-ttu-id="baa5c-200">是</span><span class="sxs-lookup"><span data-stu-id="baa5c-200">Yes</span></span>  <br/> |<span data-ttu-id="baa5c-201">是</span><span class="sxs-lookup"><span data-stu-id="baa5c-201">Yes</span></span>  <br/> |<span data-ttu-id="baa5c-202">是</span><span class="sxs-lookup"><span data-stu-id="baa5c-202">Yes</span></span>  <br/> |
|<span data-ttu-id="baa5c-203">Online</span><span class="sxs-lookup"><span data-stu-id="baa5c-203">Online</span></span>  <br/> |<span data-ttu-id="baa5c-204">Online</span><span class="sxs-lookup"><span data-stu-id="baa5c-204">Online</span></span>  <br/> |<span data-ttu-id="baa5c-205">使用者名稱/密碼</span><span class="sxs-lookup"><span data-stu-id="baa5c-205">Username/Password</span></span>  <br/> |<span data-ttu-id="baa5c-206">是</span><span class="sxs-lookup"><span data-stu-id="baa5c-206">Yes</span></span>  <br/> |<span data-ttu-id="baa5c-207">是</span><span class="sxs-lookup"><span data-stu-id="baa5c-207">Yes</span></span>  <br/> |<span data-ttu-id="baa5c-208">否</span><span class="sxs-lookup"><span data-stu-id="baa5c-208">No</span></span>  <br/> |
|<span data-ttu-id="baa5c-209">Online</span><span class="sxs-lookup"><span data-stu-id="baa5c-209">Online</span></span>  <br/> |<span data-ttu-id="baa5c-210">內部部署</span><span class="sxs-lookup"><span data-stu-id="baa5c-210">On-premises</span></span>  <br/> |<span data-ttu-id="baa5c-211">網頁登入</span><span class="sxs-lookup"><span data-stu-id="baa5c-211">Web Sign-in</span></span>  <br/> |<span data-ttu-id="baa5c-212">是</span><span class="sxs-lookup"><span data-stu-id="baa5c-212">Yes</span></span>  <br/> |<span data-ttu-id="baa5c-213">否</span><span class="sxs-lookup"><span data-stu-id="baa5c-213">No</span></span>  <br/> |<span data-ttu-id="baa5c-214">否</span><span class="sxs-lookup"><span data-stu-id="baa5c-214">No</span></span>  <br/> |
|<span data-ttu-id="baa5c-215">Online</span><span class="sxs-lookup"><span data-stu-id="baa5c-215">Online</span></span>  <br/> |<span data-ttu-id="baa5c-216">內部部署</span><span class="sxs-lookup"><span data-stu-id="baa5c-216">On-Premises</span></span>  <br/> |<span data-ttu-id="baa5c-217">使用者名稱/密碼</span><span class="sxs-lookup"><span data-stu-id="baa5c-217">Username/Password</span></span>  <br/> |<span data-ttu-id="baa5c-218">是</span><span class="sxs-lookup"><span data-stu-id="baa5c-218">Yes</span></span>  <br/> |<span data-ttu-id="baa5c-219">是</span><span class="sxs-lookup"><span data-stu-id="baa5c-219">Yes</span></span>  <br/> |<span data-ttu-id="baa5c-220">否</span><span class="sxs-lookup"><span data-stu-id="baa5c-220">No</span></span>  <br/> |
|<span data-ttu-id="baa5c-221">內部部署</span><span class="sxs-lookup"><span data-stu-id="baa5c-221">On-premises</span></span>  <br/> |<span data-ttu-id="baa5c-222">線上/內部部署</span><span class="sxs-lookup"><span data-stu-id="baa5c-222">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="baa5c-223">PIN 驗證</span><span class="sxs-lookup"><span data-stu-id="baa5c-223">PIN Authentication</span></span>  <br/> |<span data-ttu-id="baa5c-224">是</span><span class="sxs-lookup"><span data-stu-id="baa5c-224">Yes</span></span>  <br/> |<span data-ttu-id="baa5c-225">否</span><span class="sxs-lookup"><span data-stu-id="baa5c-225">No</span></span>  <br/> |<span data-ttu-id="baa5c-226">否</span><span class="sxs-lookup"><span data-stu-id="baa5c-226">No</span></span>  <br/> |
|<span data-ttu-id="baa5c-227">內部部署</span><span class="sxs-lookup"><span data-stu-id="baa5c-227">On-premises</span></span>  <br/> |<span data-ttu-id="baa5c-228">線上/內部部署</span><span class="sxs-lookup"><span data-stu-id="baa5c-228">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="baa5c-229">使用者名稱/密碼</span><span class="sxs-lookup"><span data-stu-id="baa5c-229">Username/Password</span></span>  <br/> |<span data-ttu-id="baa5c-230">是</span><span class="sxs-lookup"><span data-stu-id="baa5c-230">Yes</span></span>  <br/> |<span data-ttu-id="baa5c-231">是</span><span class="sxs-lookup"><span data-stu-id="baa5c-231">Yes</span></span>  <br/> |<span data-ttu-id="baa5c-232">不適用</span><span class="sxs-lookup"><span data-stu-id="baa5c-232">N/A</span></span>  <br/> |
|<span data-ttu-id="baa5c-233">內部部署</span><span class="sxs-lookup"><span data-stu-id="baa5c-233">On-premises</span></span>  <br/> |<span data-ttu-id="baa5c-234">線上/內部部署</span><span class="sxs-lookup"><span data-stu-id="baa5c-234">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="baa5c-235">透過 PC 登入（BTOE）</span><span class="sxs-lookup"><span data-stu-id="baa5c-235">Sign-in via PC (BTOE)</span></span>  <br/> |<span data-ttu-id="baa5c-236">是</span><span class="sxs-lookup"><span data-stu-id="baa5c-236">Yes</span></span>  <br/> |<span data-ttu-id="baa5c-237">是</span><span class="sxs-lookup"><span data-stu-id="baa5c-237">Yes</span></span>  <br/> |<span data-ttu-id="baa5c-238">不適用</span><span class="sxs-lookup"><span data-stu-id="baa5c-238">N/A</span></span>  <br/> |
   
- <span data-ttu-id="baa5c-239">**電話功能**根據 IP 電話夥伴，功能集可能會稍有不同。</span><span class="sxs-lookup"><span data-stu-id="baa5c-239">**Phone features** The feature set may vary slightly based on the IP phone partner.</span></span> <span data-ttu-id="baa5c-240">若要取得完整的功能集，以及每個電話製造商功能的詳細資訊，請參閱[取得商務用 Skype Online 的電話](getting-phones-for-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="baa5c-240">For the complete feature set and for more information on the features for each phone manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
    
- <span data-ttu-id="baa5c-241">**電話鎖定**是商務用 Skype 認證手機中的最近推出的功能，用來保護電話。</span><span class="sxs-lookup"><span data-stu-id="baa5c-241">**Phone-Lock** is a recently introduced feature in Skype for Business certified phones that is used to secure a phone.</span></span> <span data-ttu-id="baa5c-242">如果已啟用，將會要求使用者在驗證成功時建立 PIN。</span><span class="sxs-lookup"><span data-stu-id="baa5c-242">If enabled, users will be asked to create a PIN upon successful authentication.</span></span> <span data-ttu-id="baa5c-243">一旦建立，手機會在您定義的空閒超時過期時鎖定，使用者會手動鎖定其手機，或使用電話配對將手機鎖與其電腦鎖同步處理。</span><span class="sxs-lookup"><span data-stu-id="baa5c-243">Once created, phones will lock when the idle-timeout that you define expires, a user manually locks their phone, or they sync their phone-lock with their PC lock using Phone Pairing.</span></span> <span data-ttu-id="baa5c-244">如果電話鎖定 PIN 輸入錯誤數次，手機將會登入使用者，或需要系統管理員的程式碼來解除鎖定電話，但這會視電話夥伴而定。</span><span class="sxs-lookup"><span data-stu-id="baa5c-244">If the phone-lock PIN is entered wrong several times, the phone will either sign the user out or require an administrator's code to unlock the phone, but this will vary depending on the phone partner.</span></span> <span data-ttu-id="baa5c-245">使用者的 PIN 應該介於6到15位數。</span><span class="sxs-lookup"><span data-stu-id="baa5c-245">The user's PIN should be between 6 and 15 digits.</span></span>
    
    <span data-ttu-id="baa5c-246">您可以停用貴組織的電話封鎖功能（預設為啟用）、變更空閒超時，以及選擇使用者是否可以在來電時撥打或使用 inband 設定。</span><span class="sxs-lookup"><span data-stu-id="baa5c-246">You can disable Phone-Lock for your organization (which is enabled by default), change the idle-timeout, and choose whether users can make phone calls while they are locked or not using inband-settings.</span></span> <span data-ttu-id="baa5c-247">如需這些設定的詳細資訊，請參閱[設定 CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps) 。</span><span class="sxs-lookup"><span data-stu-id="baa5c-247">See [Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps) for more details on those settings.</span></span>
    
## <a name="step-7-optional---if-you-have-device-pairing-and-better-together-over-ethernet-btoe"></a><span data-ttu-id="baa5c-248">步驟7（選用）-如果您有裝置配對，且搭配乙太網路更好地搭配（BToE）</span><span class="sxs-lookup"><span data-stu-id="baa5c-248">Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)</span></span>
<span data-ttu-id="baa5c-249"><a name="BK_BTOE"> </a></span><span class="sxs-lookup"><span data-stu-id="baa5c-249"><a name="BK_BTOE"> </a></span></span>

<span data-ttu-id="baa5c-250">BToE 是一種手機 paining 機制，可讓合作夥伴 IP 電話使用其 Windows Skype for Business app 來配對使用者的手機。</span><span class="sxs-lookup"><span data-stu-id="baa5c-250">BToE is a phone paining mechanism for Partner IP phones that pairs a user's phone with their Windows Skype for Business app.</span></span> <span data-ttu-id="baa5c-251">BToE 可讓使用者：</span><span class="sxs-lookup"><span data-stu-id="baa5c-251">BToE enables users to:</span></span>
  
- <span data-ttu-id="baa5c-252">使用商務用 Skype 桌面應用程式登入其 IP 電話（使用電腦）</span><span class="sxs-lookup"><span data-stu-id="baa5c-252">Sign in to their IP phone using their Skype for Business desktop app (using a PC)</span></span>
    
- <span data-ttu-id="baa5c-253">同步處理電話鎖與電腦鎖</span><span class="sxs-lookup"><span data-stu-id="baa5c-253">Synchronize Phone-Lock with PC lock</span></span>
    
- <span data-ttu-id="baa5c-254">按一下以進行通話</span><span class="sxs-lookup"><span data-stu-id="baa5c-254">Click to call</span></span>
    
<span data-ttu-id="baa5c-255">BToE 可以設定為以兩種模式運作： [*自動*（預設）] 和 [*手動*]。</span><span class="sxs-lookup"><span data-stu-id="baa5c-255">BToE can be configured to operate in two modes:  *Auto*  (default) and *Manual*  .</span></span> <span data-ttu-id="baa5c-256">您也可以使用商務用 Skype 內設定中的使用者啟用（預設）/disabled。</span><span class="sxs-lookup"><span data-stu-id="baa5c-256">It can also be enabled (default)/disabled for users using Skype for Business in-band settings.</span></span> <span data-ttu-id="baa5c-257">在*手動*模式下作業時，使用者必須執行額外步驟，將手機與其 Windows app 配對。</span><span class="sxs-lookup"><span data-stu-id="baa5c-257">When operating in *Manual*  mode, users will have to take an additional step to pair their phone with their Windows app.</span></span>
  
 <span data-ttu-id="baa5c-258">**若要將 BToE 部署至使用者**</span><span class="sxs-lookup"><span data-stu-id="baa5c-258">**To deploy BToE to users**</span></span>
  
1. <span data-ttu-id="baa5c-259">使用電腦埠將其電腦連線到他們的手機。</span><span class="sxs-lookup"><span data-stu-id="baa5c-259">Connect their PC to their phone using the PC port.</span></span>
    
     ![螢幕擷取畫面顯示與電腦的連線](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. <span data-ttu-id="baa5c-261">從以下連結，從製造商網站下載並安裝最新的 BToE 軟體。</span><span class="sxs-lookup"><span data-stu-id="baa5c-261">Download and install the latest BToE software from the manufacturer website from the links below.</span></span> <span data-ttu-id="baa5c-262">若要取得更佳的使用者體驗，您可以使用系統管理員發佈方案（例如 Microsoft 端點設定管理員）分發及安裝 BToE 軟體。</span><span class="sxs-lookup"><span data-stu-id="baa5c-262">For a better user experience, you can distribute and install the BToE software using an admin distribution solution such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="baa5c-263">如需使用 Configuration Manager 的說明，請參閱[Configuration manager 中的套件與程式](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs)。</span><span class="sxs-lookup"><span data-stu-id="baa5c-263">For help using Configuration Manager, See [Packages and programs in Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs).</span></span>
    
   - [<span data-ttu-id="baa5c-264">Polycom BToE 軟體下載網站</span><span class="sxs-lookup"><span data-stu-id="baa5c-264">Polycom BToE Software Download site</span></span>](https://www.polycom.com/voice-conferencing-solutions/microsoft-phones.html)
    
   - [<span data-ttu-id="baa5c-265">Yealink BToE 軟體下載</span><span class="sxs-lookup"><span data-stu-id="baa5c-265">Yealink BToE Software Download</span></span>](http://www.yealink.com/products_list_10.html)
    
   - [<span data-ttu-id="baa5c-266">AudioCodes BToE 軟體下載</span><span class="sxs-lookup"><span data-stu-id="baa5c-266">AudioCodes BToE Software Downloads</span></span>](https://www.audiocodes.com/solutions-products/solutions/skype-for-business-microsoft-teams/skype-for-business-online)
    
3. <span data-ttu-id="baa5c-267">BToE 的伺服器設定設定為 [**啟用**]，而且預設為 [**自動模式]** 。</span><span class="sxs-lookup"><span data-stu-id="baa5c-267">The server setting for BToE is set to **Enabled** and **Auto mode** by default.</span></span> <span data-ttu-id="baa5c-268">若要變更這些設定，請參閱[設定 CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx)。</span><span class="sxs-lookup"><span data-stu-id="baa5c-268">To change those settings, see [Set-CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx).</span></span>
    
> [!NOTE]
> <span data-ttu-id="baa5c-269">Mac 和 VDI 平臺目前不支援 BToE。</span><span class="sxs-lookup"><span data-stu-id="baa5c-269">BToE isn't currently supported on Mac and VDI platforms.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="baa5c-270">相關主題</span><span class="sxs-lookup"><span data-stu-id="baa5c-270">Related topics</span></span>
[<span data-ttu-id="baa5c-271">取得商務用 Skype 和 Microsoft Teams 的服務電話號碼</span><span class="sxs-lookup"><span data-stu-id="baa5c-271">Getting service phone numbers for Skype for Business and Microsoft Teams</span></span>](../../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)

[<span data-ttu-id="baa5c-272">以下是您在 Office 365 中使用電話系統所取得的結果</span><span class="sxs-lookup"><span data-stu-id="baa5c-272">Here's what you get with Phone System in Office 365</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="baa5c-273">音訊會議與通話方案的適用國家/地區</span><span class="sxs-lookup"><span data-stu-id="baa5c-273">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 
