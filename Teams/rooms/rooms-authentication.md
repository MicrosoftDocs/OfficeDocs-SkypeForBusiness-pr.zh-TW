---
title: 在 Microsoft Teams 會議室
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-collaboration
description: 瞭解如何設定新式驗證Microsoft Teams 會議室
ms.openlocfilehash: 93577c74005c8ad266739da0991f31e384a57ba6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117481"
---
# <a name="authentication-in-microsoft-teams-rooms"></a><span data-ttu-id="ac1e4-103">在 Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="ac1e4-103">Authentication in Microsoft Teams Rooms</span></span>

<span data-ttu-id="ac1e4-104">在應用程式層級Microsoft Teams 會議室裝置的帳戶管理。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-104">Account management for Microsoft Teams Rooms devices is handled at the application level.</span></span> <span data-ttu-id="ac1e4-105">應用程式會連接到 Microsoft Teams、商務用 Skype和Exchange，以取得會議室帳戶的資源，以啟用通話和會議體驗。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-105">The application connects to Microsoft Teams, Skype for Business, and Exchange to get resources for the room account to enable calling and meeting experiences.</span></span> <span data-ttu-id="ac1e4-106">裝置會保持帳戶不可知，以允許一直使用功能、通話案例 (適用于使用通話方案) 的裝置，以及在這些裝置上執行的自訂鎖定機制。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-106">The device is kept account agnostic to allow for always-on capabilities, calling scenarios (for devices configured with a Calling Plan), and custom lockdown mechanisms implemented on these devices.</span></span> <span data-ttu-id="ac1e4-107">這表示這些裝置驗證的方式與使用者裝置不同。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-107">This means that authentication for these devices happen in a different way than for end-user devices.</span></span>  

<span data-ttu-id="ac1e4-108">建議所有使用新式驗證Microsoft Teams 會議室或Microsoft 365 Office 365。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-108">Modern authentication is recommended for all customers using Microsoft Teams Rooms devices with Microsoft 365 or Office 365.</span></span> <span data-ttu-id="ac1e4-109">如果您有內部部署 Exchange 或 商務用 Skype 伺服器，請設定與 Azure Active Directory (Azure AD) 混合式新式驗證，以啟用新式驗證。 [](/office365/enterprise/hybrid-modern-auth-overview)</span><span class="sxs-lookup"><span data-stu-id="ac1e4-109">If you have an on-premises deployment of Exchange server or Skype for Business server, configure [hybrid modern authentication](/office365/enterprise/hybrid-modern-auth-overview) with Azure Active Directory (Azure AD) to enable using modern authentication.</span></span>

<span data-ttu-id="ac1e4-110">4.4.25.0 Microsoft Teams 會議室版本支援新式驗證。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-110">Modern authentication is supported on Microsoft Teams Rooms version 4.4.25.0 and later.</span></span>

## <a name="modern-authentication"></a><span data-ttu-id="ac1e4-111">新式驗證</span><span class="sxs-lookup"><span data-stu-id="ac1e4-111">Modern authentication</span></span>

<span data-ttu-id="ac1e4-112">當您在 Microsoft Teams 會議室 應用程式中使用新式驗證時，Active Directory 驗證庫 (ADAL) 會用來連接到 Microsoft Teams、Exchange 和 商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-112">When you use modern authentication with the Microsoft Teams Rooms application, Active Directory Authentication Library (ADAL) is used to connect to Microsoft Teams, Exchange, and Skype for Business.</span></span> <span data-ttu-id="ac1e4-113">Microsoft Teams 會議室裝置是共用裝置，而且會執行夜間重新開機，以確保運作順暢，並取得重要的作業系統、驅動程式、固件或應用程式更新。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-113">A Microsoft Teams Rooms device is a shared device and performs a nightly reboot to ensure smooth functioning and to get critical operating system, driver, firmware, or application updates.</span></span> <span data-ttu-id="ac1e4-114">新式驗證機制使用 OAuth 2.0 中的資源擁有者 [密碼認證](/azure/active-directory/develop/v2-oauth-ropc) 授權授權類型，這不需要任何使用者介入。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-114">The modern authentication mechanism uses the [resource owner password credentials](/azure/active-directory/develop/v2-oauth-ropc) authorization grant type in OAuth 2.0, which doesn't require any user intervention.</span></span> <span data-ttu-id="ac1e4-115">這是新式驗證對於使用者帳戶運作方式與應用程式所使用的資源帳戶Microsoft Teams 會議室差異之一。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-115">This is one of the key differences between how modern authentication works for user accounts versus resource accounts that are used by the Microsoft Teams Rooms application.</span></span> <span data-ttu-id="ac1e4-116">因此，Microsoft Teams 會議室資源帳戶不應被配置為使用多重要素驗證 (MFA) 、智慧卡驗證或用戶端憑證式驗證 (這些都可供使用者) 使用。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-116">Because of this, Microsoft Teams Rooms resource accounts shouldn't be configured to use multi-factor authentication (MFA), smart card authentication, or client certificate-based authentication (which are all available for end users).</span></span>

<span data-ttu-id="ac1e4-117">新式驗證在 Microsoft Teams 會議室 裝置和使用者裝置上運作方式的另一個關鍵差異是，當您使用此授權類型時，無法使用資源帳戶在 Azure Active Directory 和 端點管理員 中將裝置層級的條件式存取原則當做裝置資訊傳遞。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-117">The other key difference between how modern authentication works on Microsoft Teams Rooms devices and end-user devices is that you can't use a resource account to apply device-level conditional access policies in Azure Active Directory and Endpoint Manager as device info is not passed when using this grant type.</span></span> <span data-ttu-id="ac1e4-118">您可以改為在會議室中註冊Microsoft 端點管理員，然後使用使用 Intune 管理會議室Teams所提供的指引來適用[合規性原則](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-118">Instead, you can enroll a device in Microsoft Endpoint Manager and apply compliance policies by using the guidance provided in [Managing Teams Meeting Rooms with Intune](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230).</span></span>

## <a name="enable-modern-authentication-on-a-microsoft-teams-rooms-device"></a><span data-ttu-id="ac1e4-119">在裝置上啟用新式Microsoft Teams 會議室驗證</span><span class="sxs-lookup"><span data-stu-id="ac1e4-119">Enable modern authentication on a Microsoft Teams Rooms device</span></span>

<span data-ttu-id="ac1e4-120">若要Microsoft Teams 會議室使用新式驗證商務用 Skype Exchange，請啟用新裝置上新式驗證的用戶端Microsoft Teams 會議室設定。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-120">For Microsoft Teams Rooms to use modern authentication with Skype for Business and Exchange, enable the client-side setting for modern authentication on the Microsoft Teams Rooms device.</span></span> <span data-ttu-id="ac1e4-121">您可以在裝置設定或 XML 設定檔中執行此操作。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-121">You can do this in the device settings or in the XML config file.</span></span>

> [!NOTE]
> <span data-ttu-id="ac1e4-122">啟用新式驗證的用戶端設定之前，請確定您的環境已正確設定為使用新式驗證。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-122">Before you enable the client-side setting for modern authentication, make sure that your environment is set up correctly to use modern authentication.</span></span>

### <a name="using-device-settings"></a><span data-ttu-id="ac1e4-123">使用裝置設定</span><span class="sxs-lookup"><span data-stu-id="ac1e4-123">Using device settings</span></span>

1. <span data-ttu-id="ac1e4-124">在 Microsoft 小組會議室裝置上，**前往其他 (** **...) 。**</span><span class="sxs-lookup"><span data-stu-id="ac1e4-124">On the Microsoft Team Rooms device, go to **More** (**...**).</span></span>
    
2. <span data-ttu-id="ac1e4-125">選取 **設定**，然後輸入裝置系統管理員的使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-125">Select **Settings**, and then enter the device administrator username and password.</span></span>
3. <span data-ttu-id="ac1e4-126">請前往帳戶 **選項卡** ，開啟 **新式驗證**，然後選取儲存 **並離開**。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-126">Go to the **Account** tab, turn on **Modern Authentication**, and then select **Save and exit**.</span></span>

### <a name="using-the-xml-config-file"></a><span data-ttu-id="ac1e4-127">使用 XML 設定檔</span><span class="sxs-lookup"><span data-stu-id="ac1e4-127">Using the XML config file</span></span>

<span data-ttu-id="ac1e4-128">在 SkypeSettings.xml檔案中，將新式驗證 XML 元素設為 **True，** 如下所示。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-128">In your SkypeSettings.xml file, set the modern authentication XML element to **True**, as follows.</span></span>

```
<ModernAuthEnabled>True</ModernAuthEnabled>
```

<span data-ttu-id="ac1e4-129">若要適用設定，請參閱使用 XML 設定檔Microsoft Teams 會議室管理主機[設定](xml-config-file.md)。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-129">To apply the setting, see [Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file](xml-config-file.md).</span></span>

## <a name="prepare-your-environment-for-modern-authentication"></a><span data-ttu-id="ac1e4-130">準備您的環境進行新式驗證</span><span class="sxs-lookup"><span data-stu-id="ac1e4-130">Prepare your environment for modern authentication</span></span>

<span data-ttu-id="ac1e4-131">開始之前，請確定您瞭解要用於 Office 365 Azure AD 的身分識別模型。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-131">Before you begin, make sure you understand the identity models to use with Office 365 and Azure AD.</span></span> <span data-ttu-id="ac1e4-132">您可以在您的身分識別Office 365和[](/Office365/Enterprise/about-office-365-identity)Azure Active Directory，以及混合式身分識別與目錄同步處理Microsoft 365[或](/Office365/Enterprise/plan-for-directory-synchronization)Office 365。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-132">You can find more information at [Office 365 identity models and Azure Active Directory](/Office365/Enterprise/about-office-365-identity) and at [Hybrid identity and directory synchronization for Microsoft 365 or Office 365](/Office365/Enterprise/plan-for-directory-synchronization).</span></span>

### <a name="enable-modern-authentication-in-microsoft-365-or-office-365"></a><span data-ttu-id="ac1e4-133">在 Microsoft 365 或 Office 365</span><span class="sxs-lookup"><span data-stu-id="ac1e4-133">Enable modern authentication in Microsoft 365 or Office 365</span></span>

<span data-ttu-id="ac1e4-134">若要開啟新式驗證Exchange Online，請參閱在 Exchange Online[中啟用新式Exchange Online。](/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)</span><span class="sxs-lookup"><span data-stu-id="ac1e4-134">To turn on modern authentication for Exchange Online, see [Enable modern authentication in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span></span> <span data-ttu-id="ac1e4-135">如果您使用線上商務用 Skype，您也應該確認已開啟適用于線上商務用 Skype新式驗證。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-135">If you use Skype for Business Online, you should also make sure that modern authentication is turned on for Skype for Business Online.</span></span> <span data-ttu-id="ac1e4-136">若要深入瞭解，請參閱線上[商務用 Skype：啟用您的租使用者進行新式驗證](https://aka.ms/SkypeModernAuth)。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-136">To learn more, see [Skype for Business Online: Enable your tenant for modern authentication](https://aka.ms/SkypeModernAuth).</span></span>

<span data-ttu-id="ac1e4-137">我們建議您不要移除 Exchange Online 的基本驗證政策，或停用租使用者的基本驗證，直到您驗證 Microsoft Teams 會議室 裝置可以順利使用 Exchange Online、Teams 和 商務用 Skype Online 進行登錄。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-137">We recommended that you do not remove basic authentication policies for Exchange Online or disable basic authentication for your tenant until you have validated that Microsoft Teams Rooms devices can successfully sign in with Exchange Online, Teams, and Skype for Business Online.</span></span>

<span data-ttu-id="ac1e4-138">若要在 Exchange Online 中停用基本驗證Exchange Online，請參閱在 Exchange Online 中[停用基本Exchange Online。](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)</span><span class="sxs-lookup"><span data-stu-id="ac1e4-138">For more information about disabling basic authentication in Exchange Online, see [Disable Basic authentication in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online).</span></span>

## <a name="hybrid-modern-authentication"></a><span data-ttu-id="ac1e4-139">混合式新式驗證</span><span class="sxs-lookup"><span data-stu-id="ac1e4-139">Hybrid modern authentication</span></span>

<span data-ttu-id="ac1e4-140">若要確保內部部署 Exchange 伺服器和/或 商務用 Skype 伺服器的驗證成功，您必須確定已將 Microsoft Teams 會議室 一起使用的資源帳戶已配置為從 Azure AD 取得授權。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-140">To ensure successful authentication to your on-premises Exchange server and/or Skype for Business server, you must make sure the resource account that's used with Microsoft Teams Rooms is configured to get authorization from Azure AD.</span></span> 

<span data-ttu-id="ac1e4-141">Teams 會議室驗證流程會因您的驗證組組而異。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-141">Teams Rooms authentication flows vary depending on your authentication configuration.</span></span> <span data-ttu-id="ac1e4-142">對於使用受管理網域的客戶，Teams 會議室[使用 OAuth 2.0 資源擁有者密碼](/azure/active-directory/develop/v2-oauth-ropc)認證Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-142">For customers using a managed domain, Teams Rooms uses [OAuth 2.0 Resource Owner Password Credentials](/azure/active-directory/develop/v2-oauth-ropc) with Azure Active Directory.</span></span> <span data-ttu-id="ac1e4-143">不過，對於使用聯盟網域的客戶，會使用[OAuth 2.0 SAML Bearer Flow](/azure/active-directory/develop/v2-saml-bearer-assertion)聲明。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-143">However, for customers using a federated domain, [OAuth 2.0 SAML Bearer Assertion Flow](/azure/active-directory/develop/v2-saml-bearer-assertion) is used.</span></span>

> [!NOTE]
> <span data-ttu-id="ac1e4-144">您的身分識別提供者可能需要特定設定或設定，Azure Active Directory或Office 365。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-144">Your identity provider may need specific configurations or settings for integration with Azure Active Directory or Office 365.</span></span> <span data-ttu-id="ac1e4-145">如果您需要有關使用密碼進行驗證的協助，請Teams 會議室。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-145">Contact your identity provider if you need help with configuring authentication with Teams Rooms.</span></span>


### <a name="prerequisites-specific-to-microsoft-teams-rooms"></a><span data-ttu-id="ac1e4-146">您專用的先決條件Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="ac1e4-146">Prerequisites specific to Microsoft Teams Rooms</span></span>

<span data-ttu-id="ac1e4-147">混合式拓撲中啟用新式驗證的先決條件會涵蓋混合式新式驗證概觀，以及與內部部署 商務用 Skype 伺服器Exchange[的先決條件](/office365/enterprise/hybrid-modern-auth-overview)。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-147">The prerequisites to enable modern authentication in your hybrid topology are covered in [Hybrid modern authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](/office365/enterprise/hybrid-modern-auth-overview).</span></span> <span data-ttu-id="ac1e4-148">本文討論的所有先決條件都適用。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-148">All the prerequisites discussed in the article apply.</span></span>

<span data-ttu-id="ac1e4-149">不過，Microsoft Teams 會議室使用資源擁有者密碼認證[](https://tools.ietf.org/html/rfc6749#section-1.3.3)授權和基礎 REST API 進行新式驗證，因此請注意，以下是您Microsoft Teams 會議室。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-149">However, because Microsoft Teams Rooms uses [resource owner password credentials](https://tools.ietf.org/html/rfc6749#section-1.3.3) authorization and the underlying REST APIs for modern authentication, the following are important differences to be aware of that are specific to Microsoft Teams Rooms.</span></span>

- <span data-ttu-id="ac1e4-150">您必須擁有 Exchange Server 2016 CU8 或更高版本，Exchange Server 2019 CU1 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-150">You must have Exchange Server 2016 CU8 or later, or Exchange Server 2019 CU1 or later.</span></span>
- <span data-ttu-id="ac1e4-151">您必須擁有 2015 商務用 Skype Server或 2019 或商務用 Skype Server 2015 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-151">You must have Skype for Business Server 2015 CU5 or later, or Skype for Business Server 2019 or later.</span></span>
- <span data-ttu-id="ac1e4-152">無論您擁有何種拓撲，都不支援 MFA。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-152">MFA isn't supported regardless of the topology you have.</span></span>
- <span data-ttu-id="ac1e4-153">Microsoft Teams 會議室 SIP 和 UPN 不一樣。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-153">Microsoft Teams Rooms does not support SIP and UPN mismatch.</span></span> <span data-ttu-id="ac1e4-154">您必須使用相同的 UPN Microsoft Teams 會議室 SIP 建立一個帳戶，讓帳戶能夠使用。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-154">You must create a Microsoft Teams Rooms account with the same UPN and SIP for it to work.</span></span>
- <span data-ttu-id="ac1e4-155">如果您使用 Azure AD 支援的協力廠商驗證提供者，它必須支援透過 WS-Trust 進行的活動驗證流程。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-155">If you use a third-party authentication provider that's supported by Azure AD, it must support an active authentication flow through WS-Trust.</span></span>
- <span data-ttu-id="ac1e4-156">請勿針對使用應用程式所配置的資源帳戶使用裝置層級的條件式存取策略。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-156">Do not use device-level conditional access policies for a resource account configured with the application.</span></span> <span data-ttu-id="ac1e4-157">這麼做會導致登錄失敗。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-157">Doing so will result in sign-in failures.</span></span> <span data-ttu-id="ac1e4-158">相反地，在 Microsoft Intune中註冊裝置，然後使用 Intune 管理會議室Teams中發佈的指引來適用[合規性原則](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-158">Instead, enroll a device in Microsoft Intune and apply compliance policies by using the guidance published in [Managing Teams Meeting Rooms with Intune](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230).</span></span>

### <a name="configure-exchange-server"></a><span data-ttu-id="ac1e4-159">設定Exchange Server</span><span class="sxs-lookup"><span data-stu-id="ac1e4-159">Configure Exchange Server</span></span>

<span data-ttu-id="ac1e4-160">若要在 Exchange Server中啟用混合式新式驗證，請參閱如何Exchange Server內部部署以[使用混合式新式驗證](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-160">To enable hybrid modern authentication in Exchange Server, see [How to configure Exchange Server on-premises to use hybrid modern authentication](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication).</span></span>

### <a name="configure-skype-for-business-server"></a><span data-ttu-id="ac1e4-161">設定商務用 Skype Server</span><span class="sxs-lookup"><span data-stu-id="ac1e4-161">Configure Skype for Business Server</span></span>

<span data-ttu-id="ac1e4-162">若要啟用混合式新式驗證商務用 Skype Server，請參閱如何[商務用 Skype內部部署以使用混合式新式驗證](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-162">To enable hybrid modern authentication with Skype for Business Server, see [How to configure Skype for Business on-premises to use hybrid modern authentication](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication).</span></span>

### <a name="remove-or-disable-skype-for-business-and-exchange"></a><span data-ttu-id="ac1e4-163">移除或停用商務用 Skype Exchange</span><span class="sxs-lookup"><span data-stu-id="ac1e4-163">Remove or disable Skype for Business and Exchange</span></span>

<span data-ttu-id="ac1e4-164">如果您的設定不允許混合式新式驗證，或您需要移除或停用 Exchange 或 商務用 Skype 的混合式新式驗證，請參閱從 商務用 Skype 和 Exchange 移除或停用混合式新式[驗證](/Office365/Enterprise/remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha)。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-164">If your setup doesn't allow for hybrid modern authentication or you need to remove or disable hybrid modern authentication for Exchange or Skype for Business, see [Removing or disabling hybrid modern authentication from Skype for Business and Exchange](/Office365/Enterprise/remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha).</span></span>

### <a name="azure-ad-conditional-access"></a><span data-ttu-id="ac1e4-165">Azure AD 條件式存取</span><span class="sxs-lookup"><span data-stu-id="ac1e4-165">Azure AD conditional access</span></span>

<span data-ttu-id="ac1e4-166">您可以設定用於 IP/Microsoft Teams 會議室存取的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-166">You can configure a resource account used with Microsoft Teams Rooms for IP/location-based access.</span></span> <span data-ttu-id="ac1e4-167">若要深入瞭解，請參閱條件 [式存取：根據位置封鎖存取](/azure/active-directory/conditional-access/howto-conditional-access-policy-location)。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-167">To learn more, see [Conditional Access: Block access by location](/azure/active-directory/conditional-access/howto-conditional-access-policy-location).</span></span>

<span data-ttu-id="ac1e4-168">不支援其他條件式存取策略。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-168">No other conditional access policies are supported.</span></span> <span data-ttu-id="ac1e4-169">有關裝置合規性詳細資訊，請參閱使用[Intune 管理Teams會議室](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)。</span><span class="sxs-lookup"><span data-stu-id="ac1e4-169">For more information about device compliance, see [Managing Teams Meeting Rooms with Intune](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230).</span></span>