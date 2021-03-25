---
title: Microsoft Teams 會議室中的驗證
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
description: 瞭解如何為 Microsoft Teams 會議室設定新式驗證
ms.openlocfilehash: 93577c74005c8ad266739da0991f31e384a57ba6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117481"
---
# <a name="authentication-in-microsoft-teams-rooms"></a>Microsoft Teams 會議室中的驗證

Microsoft Teams 會議室裝置的帳戶管理是在應用程式層級處理。 應用程式會連接到 Microsoft Teams、商務用 Skype 和 Exchange，以取得會議室帳戶的資源，以啟用通話和會議體驗。 裝置會保持帳戶不可知，以允許一直使用功能、通話案例 (適用于使用通話方案) 的裝置，以及在這些裝置上執行的自訂鎖定機制。 這表示這些裝置驗證的方式與使用者裝置不同。  

建議所有使用 Microsoft Teams 會議室裝置與 Microsoft 365 或 Office 365 的客戶使用新式驗證。 如果您有 Exchange 伺服器或商務用 Skype 伺服器內部部署，請設定[](/office365/enterprise/hybrid-modern-auth-overview)Azure Active Directory (Azure AD) 混合式新式驗證，以啟用新式驗證。

Microsoft Teams 會議室版本 4.4.25.0 及更新版本支援新式驗證。

## <a name="modern-authentication"></a>新式驗證

當您在 Microsoft Teams 會議室應用程式中使用新式驗證時，Active Directory 驗證文件庫 (ADAL) 會用來連接到 Microsoft Teams、Exchange 和商務用 Skype。 Microsoft Teams 會議室裝置是共用裝置，會執行夜間重新開機，以確保運作順暢，並取得重要的作業系統、驅動程式、固件或應用程式更新。 新式驗證機制使用 OAuth 2.0 中的資源擁有者 [密碼認證](/azure/active-directory/develop/v2-oauth-ropc) 授權授權類型，這不需要任何使用者介入。 這是新式驗證如何適用于使用者帳戶與 Microsoft Teams 會議室應用程式使用的資源帳戶之間的其中一個主要差異。 因此，Microsoft Teams 會議室資源帳戶不應被配置為使用多重要素驗證 (MFA) 、智慧卡驗證或用戶端憑證式驗證 (這些都適用于使用者) 。

新式驗證在 Microsoft Teams 會議室裝置和使用者裝置上運作方式的另一個關鍵差異是，使用此授權類型時，您不得使用資源帳戶在 Azure Active Directory 和端點管理員中將裝置層級的條件式存取原則當做裝置資訊傳遞。 您可以改為在 Microsoft 端點管理員中註冊裝置，然後使用使用 Intune 管理 Teams 會議室所提供的指引來 [適用合規性原則](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)。

## <a name="enable-modern-authentication-on-a-microsoft-teams-rooms-device"></a>在 Microsoft Teams 會議室裝置上啟用新式驗證

若要讓 Microsoft Teams 會議室在商務用 Skype 和 Exchange 中使用新式驗證，請啟用 Microsoft Teams 會議室裝置上新式驗證的用戶端設定。 您可以在裝置設定或 XML 設定檔中執行此操作。

> [!NOTE]
> 啟用新式驗證的用戶端設定之前，請確定您的環境已正確設定為使用新式驗證。

### <a name="using-device-settings"></a>使用裝置設定

1. 在 Microsoft 小組會議室裝置上，**前往其他 (** **...) 。**
    
2. 選取 **設定**，然後輸入裝置系統管理員使用者名稱和密碼。
3. 請前往帳戶 **選項卡** ，開啟 **新式驗證**，然後選取儲存 **並離開**。

### <a name="using-the-xml-config-file"></a>使用 XML 設定檔

在 SkypeSettings.xml檔案中，將新式驗證 XML 元素設為 **True，** 如下所示。

```
<ModernAuthEnabled>True</ModernAuthEnabled>
```

若要適用設定，請參閱使用 XML 設定檔遠端系統管理 [Microsoft Teams 會議室主控台設定](xml-config-file.md)。

## <a name="prepare-your-environment-for-modern-authentication"></a>準備您的環境進行新式驗證

開始之前，請務必瞭解要用於 Office 365 和 Azure AD 的身分識別模型。 您可以在 Office [365 身分](/Office365/Enterprise/about-office-365-identity) 識別模型和 Azure Active Directory 以及 Microsoft [365 或 Office 365](/Office365/Enterprise/plan-for-directory-synchronization)的混合身分識別與目錄同步處理找到詳細資訊。

### <a name="enable-modern-authentication-in-microsoft-365-or-office-365"></a>在 Microsoft 365 或 Office 365 中啟用新式驗證

若要開啟 Exchange Online 的新式驗證，請參閱在 Exchange Online 中 [啟用新式驗證](/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)。 如果您使用商務用 Skype Online，您也應該確認商務用 Skype Online 已開啟新式驗證。 若要深入瞭解，請參閱 [商務用 Skype Online：啟用租使用者進行新式驗證](https://aka.ms/SkypeModernAuth)。

我們建議您不要移除 Exchange Online 的基本驗證政策，或停用租使用者的基本驗證，直到您驗證 Microsoft Teams 會議室裝置可以順利使用 Exchange Online、Teams 和商務用 Skype Online 進行登錄。

若要進一步停用 Exchange Online 中的基本驗證，請參閱在 Exchange Online 中停用 [基本驗證](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)。

## <a name="hybrid-modern-authentication"></a>混合式新式驗證

若要確保內部部署 Exchange 伺服器和/或商務用 Skype 伺服器的驗證成功，您必須確定 Microsoft Teams 會議室所使用的資源帳戶已配置為從 Azure AD 取得授權。 

Teams 會議室驗證流程會根據您的驗證組式而不同。 對於使用受管理網域的客戶，Teams 會議室會使用 [OAuth 2.0 資源擁有者密碼認證](/azure/active-directory/develop/v2-oauth-ropc) 與 Azure Active Directory。 不過，對於使用聯盟網域的客戶，會使用 [OAuth 2.0 SAML Bearer 聲明流程](/azure/active-directory/develop/v2-saml-bearer-assertion) 。

> [!NOTE]
> 您的身分識別提供者可能需要特定設定或設定，以與 Azure Active Directory 或 Office 365 整合。 如果您需要有關使用 Teams 會議室進行驗證的協助，請與您的身分識別提供者聯繫。


### <a name="prerequisites-specific-to-microsoft-teams-rooms"></a>Microsoft Teams 會議室特有的先決條件

混合式拓撲中啟用新式驗證的先決條件會涵蓋混合式新式驗證概觀，以及使用內部部署商務用 Skype 和 Exchange 伺服器 [的先決條件](/office365/enterprise/hybrid-modern-auth-overview)。 本文討論的所有先決條件都適用。

不過，由於 Microsoft Teams[](https://tools.ietf.org/html/rfc6749#section-1.3.3)會議室使用資源擁有者密碼認證授權和基礎 REST API 進行新式驗證，因此請注意，以下是 Microsoft Teams 會議室特有的重要差異。

- 您必須擁有 Exchange Server 2016 CU8 或更新版，或 Exchange Server 2019 CU1 或更新版。
- 您必須擁有商務用 Skype Server 2015 CU5 或更新版，或商務用 Skype Server 2019 或更新版。
- 無論您擁有何種拓撲，都不支援 MFA。
- Microsoft Teams 會議室不支援 SIP 和 UPN 不一樣。 您必須使用相同的 UPN 和 SIP 建立 Microsoft Teams 會議室帳戶，讓帳戶能夠使用。
- 如果您使用 Azure AD 支援的協力廠商驗證提供者，它必須支援透過 WS-Trust 進行的活動驗證流程。
- 請勿針對使用應用程式所配置的資源帳戶使用裝置層級的條件式存取策略。 這麼做會導致登錄失敗。 請改為在 Microsoft Intune 中註冊裝置，然後使用 Intune 管理 Teams 會議室中發佈的指引 [來適用合規性原則](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)。

### <a name="configure-exchange-server"></a>設定 Exchange Server

若要在 Exchange Server 中啟用混合式新式驗證，請參閱如何將 Exchange Server 內部部署設定 [為使用混合式新式驗證](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)。

### <a name="configure-skype-for-business-server"></a>設定商務用 Skype Server

若要使用商務用 Skype Server 啟用混合式新式驗證，請參閱如何將商務用 Skype 內部部署設定 [為使用混合式新式驗證](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)。

### <a name="remove-or-disable-skype-for-business-and-exchange"></a>移除或停用商務用 Skype 和 Exchange

如果您的設定不允許混合式新式驗證，或您需要移除或停用 Exchange 或商務用 Skype 的混合式新式驗證，請參閱從商務用 Skype 和 Exchange 移除或停用混合式新式 [驗證](/Office365/Enterprise/remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha)。

### <a name="azure-ad-conditional-access"></a>Azure AD 條件式存取

您可以設定與 Microsoft Teams 會議室一起使用的資源帳戶，以取得 IP/位置式存取。 若要深入瞭解，請參閱條件 [式存取：根據位置封鎖存取](/azure/active-directory/conditional-access/howto-conditional-access-policy-location)。

不支援其他條件式存取策略。 有關裝置合規性詳細資訊，請參閱使用 [Intune 管理 Teams 會議室](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)。