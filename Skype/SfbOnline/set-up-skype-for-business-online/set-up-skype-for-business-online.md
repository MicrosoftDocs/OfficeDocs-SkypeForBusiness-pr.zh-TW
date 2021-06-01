---
title: 設定商務用 Skype Online
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 40296968-e779-4259-980b-c2de1c044c6e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Setup
- Alchemy
- LIL_Placement
- O365E_SkypeforBusinessON
- O365M_SkypeforBusinessON
- O365P_SkypeforBusinessON
description: '瞭解如何設定您的網域、使用者、IM 和目前狀態，讓貴組織安裝商務用 Skype。 另請參閱如何設定音訊會議、電話系統通話方案，以及Skype廣播。 '
ms.openlocfilehash: fcca1a3181ca0f5753fd53811290d710e8030064
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239805"
---
# <a name="set-up-skype-for-business-online"></a><span data-ttu-id="e344f-104">設定商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="e344f-104">Set up Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="e344f-105">您必須擁有全域系統管理員許可權，才能設定商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="e344f-105">You must have global admin permissions to set up Skype for Business.</span></span> <span data-ttu-id="e344f-106">如果您有限制網頁部分存取的防火牆或 Proxy 伺服器，請考慮雇用[Microsoft](https://go.microsoft.com/fwlink/?linkid=391089)合作夥伴來商務用 Skype帳戶。</span><span class="sxs-lookup"><span data-stu-id="e344f-106">If you have a firewall or proxy server that restricts access to parts of the web, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to set up Skype for Business for you.</span></span>

## <a name="setting-up-skype"></a><span data-ttu-id="e344f-107">設定Skype</span><span class="sxs-lookup"><span data-stu-id="e344f-107">Setting up Skype</span></span>

<span data-ttu-id="e344f-108">您似乎需要協助Skype訂閱Microsoft 365 Office 365帳戶。</span><span class="sxs-lookup"><span data-stu-id="e344f-108">Looks like you need help setting up Skype with your Microsoft 365 or Office 365 subscription.</span></span> <span data-ttu-id="e344f-109">您可以按照本文中的步驟完成設定。</span><span class="sxs-lookup"><span data-stu-id="e344f-109">You can follow the steps in this article to get your setup completed.</span></span>

## <a name="1-plan-for-skype-for-business"></a><span data-ttu-id="e344f-110">1. 規劃商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="e344f-110">1. Plan for Skype for Business</span></span>

<span data-ttu-id="e344f-111">如果您有標準 **[Microsoft 365 商務進階版](https://products.office.com/business/office-365-business-premium)** 商務基本版，您可以使用商務用 Skype 來撥打線上電話給您訂閱中的公司其他人員。</span><span class="sxs-lookup"><span data-stu-id="e344f-111">If you have **[Microsoft 365 Business Premium Standard](https://products.office.com/business/office-365-business-premium)** or **Business Essentials**, you can use Skype for Business to make online calls to other people in your business who are on your subscription.</span></span> <span data-ttu-id="e344f-112">例如，如果您的公司有 10 人，在執行下列步驟 2-6 之後，您就能開始使用 商務用 Skype 進行[IM](https://support.office.com/article/cc05afa6-1894-4a82-9dd9-6222061f50fd)和線上會議，以及使用[商務用 Skype](https://support.office.com/article/2eed8424-581a-4497-b505-c08c152e5851)的會議商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="e344f-112">For example, if your business has 10 people, you'll be able to [Start using Skype for Business for IM and online meetings](https://support.office.com/article/cc05afa6-1894-4a82-9dd9-6222061f50fd) each other, and [Meetings with Skype for Business](https://support.office.com/article/2eed8424-581a-4497-b505-c08c152e5851) using Skype for Business after performing the steps 2-6 below.</span></span> <span data-ttu-id="e344f-113">您也可以在[商務用 Skype](https://support.office.com/article/b8305620-d16e-4667-989d-4a977aad6556#bkmk_OWA)中Outlook線上會議！</span><span class="sxs-lookup"><span data-stu-id="e344f-113">And you can [Set up a Skype for Business meeting in Outlook](https://support.office.com/article/b8305620-d16e-4667-989d-4a977aad6556#bkmk_OWA) to online meetings, too!</span></span>

<span data-ttu-id="e344f-114">如果您想要使用電話商務用 Skype撥打和接聽來自公司 *外部人員的電話*： </span><span class="sxs-lookup"><span data-stu-id="e344f-114">If you want to use Skype for Business to make and receive **calls** from people *external*  to your business:</span></span>

- <span data-ttu-id="e344f-115">**選項 1.使用免費的 Skype [應用程式](https://www.skype.com/)**。</span><span class="sxs-lookup"><span data-stu-id="e344f-115">**Option 1. Use the free [Skype app](https://www.skype.com/)**.</span></span> <span data-ttu-id="e344f-116">如果您擁有非常小型企業 (例如 1-2) ，使用 Skype 應用程式是更好的方法。</span><span class="sxs-lookup"><span data-stu-id="e344f-116">If you have a very small business (for example, 1-2 people), using the Skype app is the better way to go.</span></span> <span data-ttu-id="e344f-117">國內及國際通話費用較低。</span><span class="sxs-lookup"><span data-stu-id="e344f-117">It's less expensive to use for domestic and international calls.</span></span> <span data-ttu-id="e344f-118">您仍然可以進行電話會議、進行視音訊通話，以及共用桌面進行簡報。</span><span class="sxs-lookup"><span data-stu-id="e344f-118">You can still hold conference calls, make video calls, and share your desktop for presentations.</span></span> <span data-ttu-id="e344f-119">[查看費率和付款選項](https://secure.skype.com/en/calling-rates?wt.mc_id=legacy&amp;expo365=bundled)。</span><span class="sxs-lookup"><span data-stu-id="e344f-119">[Check out the rates and payment options](https://secure.skype.com/en/calling-rates?wt.mc_id=legacy&amp;expo365=bundled).</span></span>

- <span data-ttu-id="e344f-120">**選項 2.升級您的方案，並購買 電話系統 電話方案及通話Office 365。**</span><span class="sxs-lookup"><span data-stu-id="e344f-120">**Option 2. Upgrade your plan, and buy the Phone System and a Calling Plan for Office 365**.</span></span> <span data-ttu-id="e344f-121">若要瞭解這項成本，然後進行切換，最簡單的方法就是與商務產品 [支援人員聯繫 -](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) 系統管理說明，讓他們幫您完成所有工作。</span><span class="sxs-lookup"><span data-stu-id="e344f-121">The easiest way to find out how much this costs, and then make the switch, is to [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) and have them do everything for you.</span></span>

<span data-ttu-id="e344f-122">若要深入瞭解，請參閱[規劃商務Office 365的設定](https://support.office.com/article/eb926624-018b-4486-bf11-5fba6ee4d645#bkmk_skype)。</span><span class="sxs-lookup"><span data-stu-id="e344f-122">To learn more, see [Plan your setup of Office 365 for business](https://support.office.com/article/eb926624-018b-4486-bf11-5fba6ee4d645#bkmk_skype).</span></span>

## <a name="2-sign-in-to-office-365"></a><span data-ttu-id="e344f-123">2. Office 365</span><span class="sxs-lookup"><span data-stu-id="e344f-123">2. Sign in to Office 365</span></span>
<span data-ttu-id="e344f-124"><a name="bkmk_signin"> </a></span><span class="sxs-lookup"><span data-stu-id="e344f-124"><a name="bkmk_signin"> </a></span></span>

<span data-ttu-id="e344f-125">商務用 SkypeOnline 是服務Office 365的一部分。</span><span class="sxs-lookup"><span data-stu-id="e344f-125">Skype for Business Online is part of the Office 365 suite of services.</span></span> <span data-ttu-id="e344f-126">若要設定 商務用 Skype Online，您必須在 Office 365。</span><span class="sxs-lookup"><span data-stu-id="e344f-126">To set up Skype for Business Online, you need to sign in to Office 365.</span></span> <span data-ttu-id="e344f-127">以下是您執行此工作的原因：</span><span class="sxs-lookup"><span data-stu-id="e344f-127">Here's how you do that:</span></span>

1. <span data-ttu-id="e344f-128">尋找您的Microsoft 365或Office 365使用者識別碼 (例如<em>，rob@fourthcoffee.com) 。</em></span><span class="sxs-lookup"><span data-stu-id="e344f-128">Locate your Microsoft 365 or Office 365 user ID (for example,  <em>rob@fourthcoffee.com</em>  ).</span></span> <span data-ttu-id="e344f-129">您收到來自 Microsoft Online Services 小組的電子郵件，其中包含您Microsoft 365或Office 365購買線上版時所建立商務用 Skype識別碼。</span><span class="sxs-lookup"><span data-stu-id="e344f-129">You received an email from the Microsoft Online Services Team that contains the Microsoft 365 or Office 365 user ID that you created when you purchased Skype for Business Online.</span></span> <span data-ttu-id="e344f-130">郵件看起來像這樣：</span><span class="sxs-lookup"><span data-stu-id="e344f-130">The mail looks something like this:</span></span>

    ![註冊線上版後收到的歡迎電子郵件範例商務用 Skype範例。](../images/977c5c96-29c5-40c0-a4c4-1ba66ba3a1fb.png)

2. <span data-ttu-id="e344f-133">請登錄系統[管理中心，](https://admin.microsoft.com)然後輸入您的Microsoft 365或Office 365使用者識別碼和密碼。</span><span class="sxs-lookup"><span data-stu-id="e344f-133">Sign in to the [admin center](https://admin.microsoft.com) and enter your Microsoft 365 or Office 365 user ID and password.</span></span> 

## <a name="3-set-up-your-domain-and-users"></a><span data-ttu-id="e344f-134">3. 設定您的網域和使用者</span><span class="sxs-lookup"><span data-stu-id="e344f-134">3. Set up your domain and users</span></span>
<span data-ttu-id="e344f-135"><a name="bkmk_users"> </a></span><span class="sxs-lookup"><span data-stu-id="e344f-135"><a name="bkmk_users"> </a></span></span>

<span data-ttu-id="e344f-136">現在，您已Office 365，您可以將網域和組織中人員設定為使用 商務用 Skype Online。</span><span class="sxs-lookup"><span data-stu-id="e344f-136">Now that you're signed in to Office 365, you can set up your domain and people in your organization to use Skype for Business Online.</span></span>

1. <span data-ttu-id="e344f-137">[新增網](https://support.office.com/article/6383f56d-3d09-4dcb-9b41-b5f5a5efd611)域和使用者至 Office 365：使用 Office 365 設定精靈來設定您的自訂網域 (，例如 *fourthcoffee.com) Office 365。*</span><span class="sxs-lookup"><span data-stu-id="e344f-137">[Add a domain and users to Office 365](https://support.office.com/article/6383f56d-3d09-4dcb-9b41-b5f5a5efd611): Use the Office 365 setup wizard to set up your custom domain (such as *fourthcoffee.com*) with Office 365.</span></span> <span data-ttu-id="e344f-138">**根據預設，Office 365設定精靈包括設定 商務用 Skype Online，以及建立您的商務用 Skype使用者 ID。**</span><span class="sxs-lookup"><span data-stu-id="e344f-138">**By default, the Office 365 setup wizard includes setting up Skype for Business Online and creating your Skype for Business user IDs.**</span></span> <span data-ttu-id="e344f-139">如果您已經使用精靈來設定您的網域Office 365，則已完成此步驟。</span><span class="sxs-lookup"><span data-stu-id="e344f-139">If you already used the wizard to set up your domain for Office 365, then you've completed this step.</span></span>

2. <span data-ttu-id="e344f-140">[檢查您的網域和 DNS 連接](https://support.office.com/article/2b54e1b0-47a7-4018-a1e4-c2b924e7c5a0)：使用我們的工具 -網域疑難排解員 -檢查您的網域和 DNS 設定是否正確。</span><span class="sxs-lookup"><span data-stu-id="e344f-140">[Check your domain and DNS connections](https://support.office.com/article/2b54e1b0-47a7-4018-a1e4-c2b924e7c5a0): Use our tool - the domains troubleshooter - to check that your domain and DNS settings are correct.</span></span> <span data-ttu-id="e344f-141">現在這麼做有助於日後找出任何設定問題，因為您可以排除 DNS 設定做為未來問題的來源。</span><span class="sxs-lookup"><span data-stu-id="e344f-141">Doing this now will go a long way to helping figure out any setup issues later since you'll be able to eliminate DNS settings as the source of future issues.</span></span>

3. <span data-ttu-id="e344f-142">Office 365 URL 和[IP 位址範圍](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO)：大部分小型企業不需要執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="e344f-142">[Office 365 URLs and IP address ranges](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO): Most small businesses don't need to do this step.</span></span> <span data-ttu-id="e344f-143">**但是，如果您有防火牆或** Proxy 伺服器限制對網頁部分的存取權限，您必須建立規則，以允許存取線上商務用 Skype端點。</span><span class="sxs-lookup"><span data-stu-id="e344f-143">**But if you have a firewall or proxy server that restricts access to parts of the web**, you must create rules to allow access to the Skype for Business Online endpoints.</span></span> <span data-ttu-id="e344f-144">這是一個進一步步驟，最好由具有防火牆和 Proxy 伺服器組組經驗的人執行。</span><span class="sxs-lookup"><span data-stu-id="e344f-144">This is an advanced step best performed by someone experienced with configuring firewalls and proxy servers.</span></span> <span data-ttu-id="e344f-145">如果您之前尚未這麼做，請考慮雇用[Microsoft 合作夥伴](https://go.microsoft.com/fwlink/?linkid=391089)來商務用 Skype您的帳戶。</span><span class="sxs-lookup"><span data-stu-id="e344f-145">If you haven't done this before, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to set up Skype for Business for you.</span></span>

## <a name="4-set-up-im-and-presence-in-your-organization"></a><span data-ttu-id="e344f-146">4. 在貴組織中設定 IM 和目前狀態</span><span class="sxs-lookup"><span data-stu-id="e344f-146">4. Set up IM and presence in your organization</span></span>
<span data-ttu-id="e344f-147"><a name="bkmk_IM"> </a></span><span class="sxs-lookup"><span data-stu-id="e344f-147"><a name="bkmk_IM"> </a></span></span>

<span data-ttu-id="e344f-148">立即訊息 (IM) 和目前狀態 ([控制](https://support.office.com/article/fea86e34-60cf-4dd0-bfb2-169a42afd92c)在 商務用 Skype) 中您目前狀態資訊的存取權是 商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="e344f-148">Instant Messaging (IM) and presence ([Control access to your presence information in Skype for Business](https://support.office.com/article/fea86e34-60cf-4dd0-bfb2-169a42afd92c)) are basic features included with Skype for Business.</span></span> <span data-ttu-id="e344f-149">根據預設，企業中的人員可以Skype和 IM。</span><span class="sxs-lookup"><span data-stu-id="e344f-149">By default, the people in your business can Skype and IM with each other.</span></span>

1. <span data-ttu-id="e344f-150">**選擇您的其他商務用 Skype使用者可以與誰通訊：**</span><span class="sxs-lookup"><span data-stu-id="e344f-150">**Choose who else your Skype for Business users can communicate with:**</span></span>

   - <span data-ttu-id="e344f-151">[允許使用者與外部使用者商務用 Skype聯絡](allow-users-to-contact-external-skype-for-business-users.md)您 *和其他* 企業都需要設定系統。</span><span class="sxs-lookup"><span data-stu-id="e344f-151">[Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md) Both you *and*  the other business will need to configure your systems.</span></span>

     <span data-ttu-id="e344f-152">**重要**：如果您的企業有兩個網域，例如 rob@contosowest.com 和 ina@contosoeast.com，您必須執行此步驟，讓所有使用者能夠彼此通訊。</span><span class="sxs-lookup"><span data-stu-id="e344f-152">**IMPORTANT**: If you have two domains in your business, such as rob@contosowest.com and ina@contosoeast.com, you need to do this step so all of your users can communicate with each other.</span></span>

   - <span data-ttu-id="e344f-153">[讓使用者商務用 Skype企業Skype連絡人](let-skype-for-business-users-add-skype-contacts.md)</span><span class="sxs-lookup"><span data-stu-id="e344f-153">[Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md) outside your business</span></span>

2. <span data-ttu-id="e344f-154">**選擇誰查看同事是否線上：** 目前狀態功能會顯示誰在線上，以及他們的可用狀態，例如可用、忙碌、離開或展示。</span><span class="sxs-lookup"><span data-stu-id="e344f-154">**Choose who sees whether co-workers are online:** The presence feature shows who's online and what their availability is, such as available, busy, away, or presenting.</span></span>

    ![包含個人訊息之人員線上狀態範例。](../images/ab6c10b4-6ad5-453c-bf0e-459b977b6e23.png)

    <span data-ttu-id="e344f-156">您可以為公司中的每個人選擇預設設定：</span><span class="sxs-lookup"><span data-stu-id="e344f-156">You can choose the default settings for everyone in your business:</span></span>

   - <span data-ttu-id="e344f-157">自動顯示人員的線上目前狀態給組織中的每個人</span><span class="sxs-lookup"><span data-stu-id="e344f-157">Automatically display a person's online presence to everyone in the organization</span></span>

   - <span data-ttu-id="e344f-158">只向連絡人顯示某人的線上目前狀態</span><span class="sxs-lookup"><span data-stu-id="e344f-158">Display a person's online presence only to their contacts</span></span>

<span data-ttu-id="e344f-159">有關指示，請參閱在 商務用 Skype [Online 中設定目前狀態](configure-presence-in-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="e344f-159">For instructions, see [Configure presence in Skype for Business Online](configure-presence-in-skype-for-business-online.md).</span></span>

## <a name="5-download-and-install-skype-for-business"></a><span data-ttu-id="e344f-160">5. 下載並安裝商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="e344f-160">5. Download and install Skype for Business</span></span>
<span data-ttu-id="e344f-161"><a name="bkmk_download"> </a></span><span class="sxs-lookup"><span data-stu-id="e344f-161"><a name="bkmk_download"> </a></span></span>

<span data-ttu-id="e344f-162">若要在商務用 Skype Mac 或行動裝置上使用，您和公司中的其他人必須先在裝置上商務用 Skype下載。</span><span class="sxs-lookup"><span data-stu-id="e344f-162">To use Skype for Business on your PC, Mac, or mobile device, you and other people in your business have to first install the Skype for Business download on your devices.</span></span>

- <span data-ttu-id="e344f-163">[安裝商務用 Skype：](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb)如何從系統管理中心下載應用程式Microsoft 365，以及如何在 PC 或 Mac 上安裝。</span><span class="sxs-lookup"><span data-stu-id="e344f-163">[Install Skype for Business](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb): Instructions for how to download the app from the Microsoft 365 admin center, and install it on your PC or Mac.</span></span>

- <span data-ttu-id="e344f-164">[在 商務用 Skype 部署](deploy-the-skype-for-business-client-in-office-365.md)Office 365 用戶端：在大型企業中部署應用程式的指示。</span><span class="sxs-lookup"><span data-stu-id="e344f-164">[Deploy the Skype for Business client in Office 365](deploy-the-skype-for-business-client-in-office-365.md): Instructions for deploying the app in a large enterprise.</span></span>

- <span data-ttu-id="e344f-165">[安裝商務用 Skype：](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb)在 Android 裝置、iOS 裝置商務用 Skype手機上下載、安裝及Windows帳戶。</span><span class="sxs-lookup"><span data-stu-id="e344f-165">[Install Skype for Business](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb): Download, install, and sign in to Skype for Business on Android devices, iOS devices, and Windows phones.</span></span>

- <span data-ttu-id="e344f-166">[開啟或關閉行動電話](turn-on-or-off-mobile-phone-notifications.md)通知：當您商務用 Skype裝置上安裝時，您和公司中的其他人可以收到有關傳入和未接立即訊息的提醒。</span><span class="sxs-lookup"><span data-stu-id="e344f-166">[Turn on or off mobile phone notifications](turn-on-or-off-mobile-phone-notifications.md): When you have Skype for Business installed on a mobile device, you and others in your business can receive alerts about incoming and missed instant messages.</span></span>

## <a name="6-test-to-make-sure-everything-is-working"></a><span data-ttu-id="e344f-167">6. 測試以確保一切正常</span><span class="sxs-lookup"><span data-stu-id="e344f-167">6. Test to make sure everything is working</span></span>
<span data-ttu-id="e344f-168"><a name="bkmk_test"> </a></span><span class="sxs-lookup"><span data-stu-id="e344f-168"><a name="bkmk_test"> </a></span></span>

<span data-ttu-id="e344f-169">首先，測試您和公司中的其他人是否可以視訊：在 商務用 Skype[中商務用 Skype。](https://support.office.com/article/8abed4b3-ac48-493e-9d76-0e10140e9451)</span><span class="sxs-lookup"><span data-stu-id="e344f-169">First, test whether you and others in your business can [Video: Sign in and out of Skype for Business](https://support.office.com/article/8abed4b3-ac48-493e-9d76-0e10140e9451).</span></span> <span data-ttu-id="e344f-170">檢查您是否可以彼此 IM、查看彼此的目前狀態，並嘗試快速會議。</span><span class="sxs-lookup"><span data-stu-id="e344f-170">Check that you can IM each other, see each other's presence, and try a quick meeting.</span></span>

<span data-ttu-id="e344f-171">問題？</span><span class="sxs-lookup"><span data-stu-id="e344f-171">Problems?</span></span> <span data-ttu-id="e344f-172">請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="e344f-172">Do the following:</span></span>

- <span data-ttu-id="e344f-173">[需要協助您商務用 Skype？](https://support.office.com/article/448b8ea7-5b33-444a-afd4-175fc9930d05)常見的登錄問題。</span><span class="sxs-lookup"><span data-stu-id="e344f-173">[Need help signing in to Skype for Business?](https://support.office.com/article/448b8ea7-5b33-444a-afd4-175fc9930d05) of common sign-in problems.</span></span>

- <span data-ttu-id="e344f-174">[請連絡商務產品的客戶支援 - 管理說明](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。</span><span class="sxs-lookup"><span data-stu-id="e344f-174">[Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span> <span data-ttu-id="e344f-175">我們在此提供協助！</span><span class="sxs-lookup"><span data-stu-id="e344f-175">We're here to help!</span></span>

## <a name="do-you-want-to-set-up-other-available-features"></a><span data-ttu-id="e344f-176">您想要設定其他可用的功能嗎？</span><span class="sxs-lookup"><span data-stu-id="e344f-176">Do you want to set up other available features?</span></span>
<span data-ttu-id="e344f-177"><a name="bkmk_more"> </a></span><span class="sxs-lookup"><span data-stu-id="e344f-177"><a name="bkmk_more"> </a></span></span>

<span data-ttu-id="e344f-178">設定更多功能之前，請確定您擁有這些功能的授權。</span><span class="sxs-lookup"><span data-stu-id="e344f-178">Before setting up more features, make sure you have licenses for them.</span></span> [<span data-ttu-id="e344f-179">商務用 Skype Microsoft Teams附加元件授權</span><span class="sxs-lookup"><span data-stu-id="e344f-179">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)

### <a name="set-up-audio-conferencing"></a><span data-ttu-id="e344f-180">設定音訊會議</span><span class="sxs-lookup"><span data-stu-id="e344f-180">Set up Audio Conferencing</span></span>

<span data-ttu-id="e344f-181">有時候，貴組織的人需要使用電話來加入會議。</span><span class="sxs-lookup"><span data-stu-id="e344f-181">Sometimes people in your organization will need to use a phone to call into a meeting.</span></span> <span data-ttu-id="e344f-182">商務用 Skype音訊會議功能，</span><span class="sxs-lookup"><span data-stu-id="e344f-182">Skype for Business includes the Audio Conferencing feature for just this situation!</span></span> <span data-ttu-id="e344f-183">使用者可以使用電話商務用 Skype會議，而不是在行動裝置商務用 Skype或 PC 上使用應用程式。</span><span class="sxs-lookup"><span data-stu-id="e344f-183">People can call into Skype for Business meetings using a phone, instead of using the Skype for Business app on a mobile device or PC.</span></span>

### <a name="set-up-phone-system-and-the-calling-plans-in-office-365"></a><span data-ttu-id="e344f-184">在 電話系統中設定通話和通話Office 365</span><span class="sxs-lookup"><span data-stu-id="e344f-184">Set up Phone System and the Calling plans in Office 365</span></span>

<span data-ttu-id="e344f-185">電話系統的Office 365功能，可為您供應商務用電話系統。</span><span class="sxs-lookup"><span data-stu-id="e344f-185">The Phone System feature in Office 365 gives you a phone system for your business.</span></span> <span data-ttu-id="e344f-186">您可以免費商務用 Skype組織的其他人員通話，而且您的員工可以接收彼此和外部來電者的語音信箱。</span><span class="sxs-lookup"><span data-stu-id="e344f-186">Calls to other Skype for Business people in your organization are free, and your employees can receive voicemail from each other and outside callers.</span></span> <span data-ttu-id="e344f-187">以下是您取得電話系統。</span><span class="sxs-lookup"><span data-stu-id="e344f-187">Here's what you get with Phone System.</span></span>

<span data-ttu-id="e344f-188">當您新增通話方案服務時，您的員工會于 商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="e344f-188">When you add the Calling Plan service, your employees get a primary phone number in Skype for Business.</span></span> <span data-ttu-id="e344f-189">他們可以撥打和接聽公司外的電話。</span><span class="sxs-lookup"><span data-stu-id="e344f-189">They can make and receive phone calls outside of your business.</span></span> <span data-ttu-id="e344f-190">他們可以在 VoIP 電話、電腦和行動裝置上撥打語音通話。</span><span class="sxs-lookup"><span data-stu-id="e344f-190">They can make voice calls across VoIP phones, PCs, and mobile devices.</span></span> <span data-ttu-id="e344f-191">萬一發生緊急事件，他們可以撥打 911 以尋找協助。</span><span class="sxs-lookup"><span data-stu-id="e344f-191">And, in case of emergencies, they can call 911 for help.</span></span>

<span data-ttu-id="e344f-192">有關逐步設定指示，請參閱設定通話方案。</span><span class="sxs-lookup"><span data-stu-id="e344f-192">For step-by-step setup instructions, see Set up Calling Plans.</span></span>

### <a name="set-up-skype-meeting-broadcast"></a><span data-ttu-id="e344f-193">設定Skype廣播</span><span class="sxs-lookup"><span data-stu-id="e344f-193">Set up Skype Meeting Broadcast</span></span>

<span data-ttu-id="e344f-194">Skype會議廣播功能可讓您製作、主持及廣播多達 10，000 位出席者的會議。</span><span class="sxs-lookup"><span data-stu-id="e344f-194">Skype Meeting Broadcast is a feature that lets you produce, host, and broadcast meetings with up to 10,000 attendees.</span></span> <span data-ttu-id="e344f-195">**若要深入瞭解其運作方式，請參閱什麼是會議廣播Skype [廣播？](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)**</span><span class="sxs-lookup"><span data-stu-id="e344f-195">**To learn more about how it works, see [What is a Skype Meeting Broadcast?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)**</span></span>

<span data-ttu-id="e344f-196">以下是設定會議廣播Skype概觀：</span><span class="sxs-lookup"><span data-stu-id="e344f-196">Here's an overview of the steps to set up Skype Meeting Broadcast:</span></span>

1. <span data-ttu-id="e344f-197">[指派或移除](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)商務Office 365授權：指派商務用 Skype **線上** 或Enterprise方案授權給要主持廣播會議的每一個人。 </span><span class="sxs-lookup"><span data-stu-id="e344f-197">[Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc): Assign **Skype for Business Online** or **Enterprise Plan** licenses to everyone who is going to **host** a Broadcast meeting.</span></span>

2. <span data-ttu-id="e344f-198">[啟用Skype](../set-up-your-network-for-skype-meeting-broadcast/enable-skype-meeting-broadcast.md)廣播：根據預設，此功能不會啟用。</span><span class="sxs-lookup"><span data-stu-id="e344f-198">[Enable Skype Meeting Broadcast](../set-up-your-network-for-skype-meeting-broadcast/enable-skype-meeting-broadcast.md): By default, this feature isn't enabled.</span></span> <span data-ttu-id="e344f-199">開啟之後，您的使用者將能夠主持與貴組織中其他人的廣播會議。</span><span class="sxs-lookup"><span data-stu-id="e344f-199">After you turn it on, your users will be able to host broadcast meetings with other people in your organization.</span></span>

3. <span data-ttu-id="e344f-200">[為會議廣播](../set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md)Skype您的網路：如果您想要與組織外部的出席者主持網路研討會和其他廣播，您需要設定您的網路。</span><span class="sxs-lookup"><span data-stu-id="e344f-200">[Set up your network for Skype Meeting Broadcast](../set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md): If you want to host webinars and other broadcasts with attendees outside of your organization, you need to configure your network.</span></span>

4. <span data-ttu-id="e344f-201">[排程](https://support.office.com/article/c3995bc9-4d32-4f75-a004-3bc5c477e553)Skype廣播，並加入 Skype [](https://support.office.com/article/14689da0-821d-48d4-9035-ea762de80ebe)會議廣播：請確定廣播會議可以安排 Skype 會議廣播，然後讓某人嘗試 *https://portal.broadcast.skype.com* 加入會議。</span><span class="sxs-lookup"><span data-stu-id="e344f-201">[Schedule a Skype Meeting Broadcast](https://support.office.com/article/c3995bc9-4d32-4f75-a004-3bc5c477e553) and have a [Join a Skype Meeting Broadcast](https://support.office.com/article/14689da0-821d-48d4-9035-ea762de80ebe): Make sure broadcast meetings work by scheduling a Skype Meeting Broadcast at  *https://portal.broadcast.skype.com*  and then having someone try to join the meeting.</span></span>

## <a name="learn-about-network-connectivity-requirements"></a><span data-ttu-id="e344f-202">瞭解網路連接需求</span><span class="sxs-lookup"><span data-stu-id="e344f-202">Learn about network connectivity requirements</span></span>
<span data-ttu-id="e344f-203"><a name="bkmk_more"> </a></span><span class="sxs-lookup"><span data-stu-id="e344f-203"><a name="bkmk_more"> </a></span></span>

<span data-ttu-id="e344f-204">網路中音訊、視商務用 Skype和應用程式共用的品質受到端對端網路連接品質的嚴重影響。</span><span class="sxs-lookup"><span data-stu-id="e344f-204">The quality of audio, video, and application sharing in Skype for Business is greatly impacted by the quality of end-to-end network connectivity.</span></span> <span data-ttu-id="e344f-205">為了獲得最佳體驗，請務必確定公司網路與線上網路之間商務用 Skype連線。</span><span class="sxs-lookup"><span data-stu-id="e344f-205">For an optimal experience, it is important to make sure there is a high-quality connection between your company network and Skype for Business Online.</span></span> <span data-ttu-id="e344f-206">有關網路和調整資訊，請參閱調整[商務用 Skype線上績效](https://support.office.com/article/beec23c2-c5d6-4e84-a8af-e82aefca7802)。</span><span class="sxs-lookup"><span data-stu-id="e344f-206">For network and tuning information, see [Tune Skype for Business Online performance](https://support.office.com/article/beec23c2-c5d6-4e84-a8af-e82aefca7802).</span></span>

## <a name="all-done-setting-up-getting-started-using-skype-for-business"></a><span data-ttu-id="e344f-207">全部設定完成嗎？</span><span class="sxs-lookup"><span data-stu-id="e344f-207">All done setting up?</span></span> <span data-ttu-id="e344f-208">開始使用商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="e344f-208">Getting started using Skype for Business</span></span>
<span data-ttu-id="e344f-209"><a name="bkmk_more"> </a></span><span class="sxs-lookup"><span data-stu-id="e344f-209"><a name="bkmk_more"> </a></span></span>

<span data-ttu-id="e344f-210">[商務用 Skype：](https://support.office.com/article/8a3491a3-c095-4718-80cf-cbbe4afe4eba)請查看這份訓練主題清單，説明您快速上手！</span><span class="sxs-lookup"><span data-stu-id="e344f-210">[Skype for Business training](https://support.office.com/article/8a3491a3-c095-4718-80cf-cbbe4afe4eba): Check out this list of training topics to help you get started quickly!</span></span>

[<span data-ttu-id="e344f-211">開始商務用 Skype電話會議</span><span class="sxs-lookup"><span data-stu-id="e344f-211">Start a Skype for Business conference call</span></span>](https://support.office.com/article/8dc8ac52-91ac-4db9-8672-11551fdaf997)

[<span data-ttu-id="e344f-212">在影片中設定視商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="e344f-212">Set Video Device options in Skype for Business</span></span>](https://support.office.com/article/d09017c0-deba-4f6c-a122-9eca6604f50c)

[<span data-ttu-id="e344f-213">使用視商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="e344f-213">Make and receive a video call using Skype for Business</span></span>](https://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42)

[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]

## <a name="related-topics"></a><span data-ttu-id="e344f-214">相關主題</span><span class="sxs-lookup"><span data-stu-id="e344f-214">Related topics</span></span>
<span data-ttu-id="e344f-215"><a name="bkmk_more"> </a></span><span class="sxs-lookup"><span data-stu-id="e344f-215"><a name="bkmk_more"> </a></span></span>

[<span data-ttu-id="e344f-216">規劃線上和 商務用 Skype Server 之間的商務用 Skype連線</span><span class="sxs-lookup"><span data-stu-id="e344f-216">Plan hybrid connectivity between Skype for Business Server and Skype for Business Online</span></span>](../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)
