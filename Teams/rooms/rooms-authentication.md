---
title: Microsoft Teams 會議室 中的驗證
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: ''
ms.collection:
- M365-collaboration
description: 瞭解如何為Microsoft Teams 會議室設定新式驗證
ms.openlocfilehash: 5667b4bc2ab356ff9776282a6142a22abd33caa1
ms.sourcegitcommit: 726df9ecac561bda18e349a5adab9bc85e52844d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2022
ms.locfileid: "65760875"
---
# <a name="authentication-in-microsoft-teams-rooms"></a>Microsoft Teams 會議室 中的驗證

Microsoft Teams 會議室帳戶管理會在應用程式層級處理。 應用程式會連線至Microsoft Teams、商務用 Skype和Exchange，以取得資源帳戶的資源，以啟用通話和會議體驗。 Teams 會議室使用專用的資源帳戶來允許隨時隨地使用功能、針對已設定通話方案) 的裝置 (通話案例，以及自訂鎖定機制。 這表示Teams 會議室的驗證方式與使用者裝置不同。  

建議所有使用Microsoft Teams 會議室搭配Microsoft 365或Office 365的客戶使用新式驗證。 如果您擁有Exchange伺服器或商務用 Skype伺服器的內部部署，請使用 Azure Active Directory (Azure AD) 設定[混合式新式驗證](/office365/enterprise/hybrid-modern-auth-overview)，以啟用新式驗證。

Microsoft Teams 會議室版本 4.4.25.0 和更新版本支援新式驗證。

## <a name="modern-authentication"></a>新式驗證

當您搭配Microsoft Teams 會議室應用程式使用新式驗證時，Active Directory Authentication Library (ADAL) 會用來連線至 Microsoft Teams、Exchange 和 商務用 Skype。 新式驗證機制使用 OAuth 2.0 中的 [資源擁有者密碼認證](/azure/active-directory/develop/v2-oauth-ropc) 授權授與類型，不需要任何使用者介入。 這是使用者帳戶的新式驗證與Microsoft Teams 會議室使用的資源帳戶之間的主要差異之一。 因此，Microsoft Teams 會議室資源帳戶不應設定為使用多重要素驗證 (MFA) 、智慧卡驗證或用戶端憑證式驗證 (，這些都適用于使用者) 。

新式驗證在Microsoft Teams 會議室和使用者裝置上運作方式的另一個主要差異在於，您無法使用資源帳戶在Azure Active Directory中套用裝置層級的條件式存取原則，而使用此授與類型時，端點管理員裝置資訊則不會傳遞。 您可以改為在Microsoft 端點管理員中註冊裝置，並套用合規性原則。 如需詳細資訊，請參閱[Microsoft Teams 會議室的條件式存取和Intune合規性](conditional-access-and-compliance-for-devices.md)。

## <a name="enable-modern-authentication-on-microsoft-teams-rooms"></a>在 Microsoft Teams 會議室 上啟用新式驗證

若要Microsoft Teams 會議室搭配商務用 Skype和Exchange使用新式驗證，請啟用用戶端設定，在 Microsoft Teams 會議室 上進行新式驗證。 您可以在裝置設定或 XML 設定檔案中執行此動作。

> [!NOTE]
> 啟用新式驗證的用戶端設定之前，請先確認您的環境設定正確，才能使用新式驗證。

### <a name="using-device-settings"></a>使用裝置設定

1. 在 Microsoft Teams 會議室 上，移至 **[其他** (**...**) 。
    
2. 選 **取 [設定**]，然後輸入裝置系統管理員的使用者名稱和密碼。
3. 移至 [ **帳戶] 索** 引標籤，開啟 [ **新式驗證]**，然後選取 [ **儲存並結束]**。

### <a name="using-the-xml-config-file"></a>使用 XML 設定檔案

在SkypeSettings.xml檔案中，將新式驗證 XML 元素設定為 **True**，如下所示。

```XML
<ModernAuthEnabled>True</ModernAuthEnabled>
```

若要套用此設定，請參閱[使用 XML 組態檔從遠端系統管理Microsoft Teams 會議室主機設定](xml-config-file.md)。

## <a name="prepare-your-environment-for-modern-authentication"></a>為您的環境進行新式驗證做好準備

開始之前，請確定您瞭解要與 Office 365 和 Azure AD 搭配使用的身分識別模型。 如需詳細資訊，請[參閱Office 365身分識別模型和Azure Active Directory](/Office365/Enterprise/about-office-365-identity)，以及[Microsoft 365或Office 365的混合式身分識別和目錄同步](/Office365/Enterprise/plan-for-directory-synchronization)處理。

### <a name="enable-modern-authentication-in-microsoft-365-or-office-365"></a>在 Microsoft 365 或 Office 365 中啟用新式驗證

若要開啟Exchange Online的新式驗證，請參閱[在 Exchange Online 中啟用新式驗證](/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)。

我們建議您不要移除Exchange Online的基本驗證原則，或停用租使用者的基本驗證，直到您驗證Microsoft Teams 會議室裝置可以順利使用Exchange Online和Teams登入。

如需在 Exchange Online 中停用基本驗證的詳細資訊，請參閱[停用 Exchange Online 中的基本驗證](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)。

## <a name="hybrid-modern-authentication"></a>混合式新式驗證

若要確保您的內部部署Exchange伺服器和/或商務用 Skype伺服器成功驗證，您必須確定已設定與Microsoft Teams 會議室搭配使用的資源帳戶，以取得 Azure AD 的授權。

Teams 會議室驗證流程會根據您的驗證設定而有所不同。 對於使用受管理網域的客戶，Teams 會議室使用[OAuth 2.0 資源擁有者密碼認證](/azure/active-directory/develop/v2-oauth-ropc)搭配Azure Active Directory。 不過，對於使用同盟網域的客戶，系統會使用[OAuth 2.0 SAML Bearer Assertion Flow](/azure/active-directory/develop/v2-saml-bearer-assertion)。

> [!NOTE]
> 您的身分識別提供者可能需要特定的設定或設定，以與Azure Active Directory或Office 365整合。 如果您需要使用Teams 會議室設定驗證的協助，請連絡您的身分識別提供者。


### <a name="prerequisites-specific-to-microsoft-teams-rooms"></a>特定Microsoft Teams 會議室的先決條件

在混合式拓撲中啟用新式驗證的必要條件涵蓋在[混合式新式驗證概觀中，以及搭配內部部署商務用 Skype和Exchange伺服器使用](/office365/enterprise/hybrid-modern-auth-overview)該拓撲的先決條件。 本文討論的所有先決條件均適用。

不過，由於Microsoft Teams 會議室使用[資源擁有者密碼認證](https://tools.ietf.org/html/rfc6749#section-1.3.3)授權和基礎 REST API 進行新式驗證，因此請注意下列是Microsoft Teams 會議室特有的重要差異。

- 您必須Exchange Server 2016 CU8 或更新版本，或Exchange Server 2019 CU1 或更新版本。
- 您必須有 商務用 Skype Server 2015 CU5 或更新版本，或商務用 Skype Server 2019 年或更新版本。
- 無論您擁有何種拓撲，都不支援 MFA。
- Microsoft Teams 會議室不支援 SIP 和 UPN 不相符。 您必須使用相同的 UPN 和 SIP 建立Microsoft Teams 會議室帳戶，才能運作。
- 如果您使用 Azure AD 支援的協力廠商驗證提供者，它必須透過 WS 信任支援作用中的驗證流程。
- 請勿針對與應用程式一起設定的資源帳戶使用裝置層級的條件式存取原則。 這麼做會導致登入失敗。 請改為在 Microsoft Intune 中註冊裝置，並套用合規性原則。 如需詳細資訊，請參閱[Microsoft Teams 會議室的條件式存取和Intune合規性](conditional-access-and-compliance-for-devices.md)。

### <a name="configure-exchange-server"></a>設定Exchange Server

若要在 Exchange Server 中啟用混合式新式驗證，請參閱[如何設定Exchange Server內部部署以使用混合式新式驗證](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)。

### <a name="configure-skype-for-business-server"></a>設定商務用 Skype Server

若要使用商務用 Skype Server啟用混合式新式驗證，請參閱[如何設定商務用 Skype內部部署以使用混合式新式驗證](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)。

### <a name="remove-or-disable-skype-for-business-and-exchange"></a>移除或停用商務用 Skype和Exchange

如果您的設定不允許混合式新式驗證，或者您需要移除或停用Exchange或商務用 Skype的混合式新式驗證，請參閱[移除或停用商務用 Skype和Exchange的混合式新式驗證](/Office365/Enterprise/remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha)。

### <a name="azure-ad-conditional-access"></a>Azure AD 條件式存取

您可以設定與 IP/位置型存取Microsoft Teams 會議室搭配使用的資源帳戶。 若要深入瞭解，請參閱 [條件式存取：依位置封鎖存取](/azure/active-directory/conditional-access/howto-conditional-access-policy-location)。

不支援其他條件式存取原則。 如需裝置合規性的詳細資訊，請參閱[支援的條件式存取和Intune Microsoft Teams 會議室合規性原則](supported-ca-and-compliance-policies.md)。
