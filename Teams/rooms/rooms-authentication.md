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
ms.localizationpriority: medium
ms.assetid: ''
ms.collection:
- M365-collaboration
description: 瞭解如何設定新式驗證Microsoft Teams 會議室
ms.openlocfilehash: d38bf63e0ed1dc9e5cb52445fab88e617fda6169
ms.sourcegitcommit: d2c76fe7705acf6e53f7673861671b1b018813dd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/13/2022
ms.locfileid: "62015193"
---
# <a name="authentication-in-microsoft-teams-rooms"></a>在 Microsoft Teams 會議室

帳戶管理Microsoft Teams 會議室應用程式層級處理。 應用程式會連接到 Microsoft Teams、商務用 Skype，Exchange以取得資源帳戶的資源，以啟用通話和會議體驗。 Teams 會議室專用資源帳戶，以允許隨時使用功能、通話案例 (為使用通話方案) 所配置的裝置，以及自訂鎖定機制。 這表示Teams 會議室驗證的方式與使用者裝置不同。  

建議所有使用新式驗證Microsoft Teams 會議室或Microsoft 365 Office 365。 如果您有內部部署伺服器Exchange伺服器商務用 Skype，請設定混合式新式驗證Azure Active Directory (Azure AD) 使用新式驗證。 [](/office365/enterprise/hybrid-modern-auth-overview)

4.4.25.0 Microsoft Teams 會議室版本支援新式驗證。

## <a name="modern-authentication"></a>新式驗證

當您在 Microsoft Teams 會議室 應用程式中使用新式驗證時，Active Directory 驗證庫 (ADAL) 會用來連接到 Microsoft Teams、Exchange 和 商務用 Skype。 新式驗證機制使用 OAuth 2.0 中的資源擁有者 [密碼認證](/azure/active-directory/develop/v2-oauth-ropc) 授權授權類型，這不需要任何使用者介入。 這是新式驗證對於使用者帳戶運作方式與使用者所使用的資源帳戶之間的一Microsoft Teams 會議室。 因此，Microsoft Teams 會議室資源帳戶不應被配置為使用多重要素驗證 (MFA) 、智慧卡驗證或用戶端憑證式驗證 (這些驗證都適用于使用者) 。

新式驗證在 Microsoft Teams 會議室 和使用者裝置上運作方式的另一個關鍵差異是，當您使用此授權類型時，無法使用資源帳戶來在 Azure Active Directory 和 端點管理員 中將裝置層級的條件式存取原則當做裝置資訊傳遞。 您可以改為在會議室中註冊Microsoft 端點管理員，然後使用 Intune 管理會議室Teams所提供的指引來適用[合規性原則](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)。

## <a name="enable-modern-authentication-on-microsoft-teams-rooms"></a>在 Microsoft Teams 會議室

若要Microsoft Teams 會議室新式驗證與商務用 Skype Exchange，請啟用用戶端設定，以在 Microsoft Teams 會議室。 您可以在裝置設定或 XML 設定檔中執行此操作。

> [!NOTE]
> 啟用新式驗證的用戶端設定之前，請確定您的環境已正確設定為使用新式驗證。

### <a name="using-device-settings"></a>使用裝置設定

1. 在 Microsoft Teams 會議室，**請前往更多** (... **) 。**
    
2. 選取 **設定**，然後輸入裝置系統管理員的使用者名稱和密碼。
3. 前往帳戶 **選項卡** ，開啟 **新式驗證**，然後選取儲存 **並離開**。

### <a name="using-the-xml-config-file"></a>使用 XML 設定檔

在 SkypeSettings.xml檔案中，將新式驗證 XML 元素設為 **True，** 如下所示。

```XML
<ModernAuthEnabled>True</ModernAuthEnabled>
```

若要適用設定，請參閱使用 XML[設定檔Microsoft Teams 會議室管理主機設定](xml-config-file.md)。

## <a name="prepare-your-environment-for-modern-authentication"></a>準備您的環境進行新式驗證

開始之前，請確定您瞭解要用於Office 365 Azure AD。 您可以在身分識別模型和Office 365，Azure Active Directory或目錄的混合身分識別與目錄同步處理Microsoft 365[或Office 365。](/Office365/Enterprise/plan-for-directory-synchronization) [](/Office365/Enterprise/about-office-365-identity)

### <a name="enable-modern-authentication-in-microsoft-365-or-office-365"></a>在 Microsoft 365 或 Office 365

若要開啟新式驗證Exchange Online，請參閱在 Exchange Online[中啟用新式Exchange Online。](/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)

我們建議您不要移除 Exchange Online 的基本驗證政策，或停用租使用者的基本驗證，直到您驗證 Microsoft Teams 會議室 裝置可以使用 Exchange Online 和 Teams。

若要在 Exchange Online 中停用基本驗證[Exchange Online。](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)

## <a name="hybrid-modern-authentication"></a>混合式新式驗證

若要確保內部部署 Exchange 伺服器和/或 商務用 Skype 伺服器的驗證成功，您必須確定已針對 Microsoft Teams 會議室 使用的資源帳戶進行組組，才能從 Azure AD 取得授權。

Teams 會議室驗證流程會根據您的驗證組式而不同。 對於使用受管理網域的客戶，Teams 會議室[使用 OAuth 2.0 資源擁有者密碼](/azure/active-directory/develop/v2-oauth-ropc)認證Azure Active Directory。 不過，針對使用聯盟網域的客戶，會使用[OAuth 2.0 SAML Bearer Flow](/azure/active-directory/develop/v2-saml-bearer-assertion)聲明。

> [!NOTE]
> 您的身分識別提供者可能需要特定設定或設定，以與Azure Active Directory或Office 365。 如果您需要有關使用密碼進行驗證的協助，請Teams 會議室。


### <a name="prerequisites-specific-to-microsoft-teams-rooms"></a>您專用的先決條件Microsoft Teams 會議室

混合式拓撲中啟用新式驗證的先決條件會涵蓋混合式新式驗證概觀，以及與內部部署 商務用 Skype 伺服器Exchange[的先決條件](/office365/enterprise/hybrid-modern-auth-overview)。 本文討論的所有先決條件都適用。

不過，Microsoft Teams 會議室[使用資源](https://tools.ietf.org/html/rfc6749#section-1.3.3)擁有者密碼認證授權和基礎 REST API 進行新式驗證，因此請注意，以下是您Microsoft Teams 會議室。

- 您必須擁有 Exchange Server 2016 CU8 或更高版本，Exchange Server 2019 CU1 或更高版本。
- 您必須擁有 2015 商務用 Skype Server或 2019 或商務用 Skype Server 2015 或更高版本。
- 無論您擁有何種拓撲，都不支援 MFA。
- Microsoft Teams 會議室 SIP 和 UPN 不一樣。 您必須使用相同的 UPN Microsoft Teams 會議室 SIP 建立帳戶，讓帳戶能夠使用。
- 如果您使用由 Azure AD 支援的協力廠商驗證提供者，則必須支援透過 WS-Trust 進行的活動驗證流程。
- 請勿針對應用程式所配置的資源帳戶使用裝置層級的條件式存取策略。 這麼做會導致登錄失敗。 請改為在 Microsoft Intune中註冊裝置，然後使用 Intune 管理會議室Teams中發佈的指引來適用[合規性原則](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)。

### <a name="configure-exchange-server"></a>設定Exchange Server

若要在 Exchange Server中啟用混合式新式驗證，請參閱如何Exchange Server內部部署中的混合[式新式驗證。](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)

### <a name="configure-skype-for-business-server"></a>設定商務用 Skype Server

若要啟用混合式新式驗證商務用 Skype Server，請參閱如何商務用 Skype[內部部署以使用混合式新式驗證](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)。

### <a name="remove-or-disable-skype-for-business-and-exchange"></a>移除或停用商務用 Skype Exchange

如果您的設定不允許混合式新式驗證，或您需要移除或停用 Exchange 或 商務用 Skype 的混合式新式驗證，請參閱從 商務用 Skype 和 Exchange 移除[或停用](/Office365/Enterprise/remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha)混合式新式驗證。

### <a name="azure-ad-conditional-access"></a>Azure AD條件式存取

您可以設定與 IP/位置式存取Microsoft Teams 會議室一起使用的資源帳戶。 若要深入瞭解，請參閱條件 [式存取：根據位置封鎖存取](/azure/active-directory/conditional-access/howto-conditional-access-policy-location)。

不支援其他條件式存取策略。 有關裝置合規性詳細資訊，請參閱使用[Intune 管理Teams會議室](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)。
