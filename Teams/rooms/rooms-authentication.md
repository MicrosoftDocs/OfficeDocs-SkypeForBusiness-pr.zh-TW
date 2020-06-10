---
title: Microsoft 團隊聊天室中的驗證
ms.author: v-lanac
author: lanachin
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
description: 瞭解如何設定 Microsoft 團隊聊天室的新式驗證
ms.openlocfilehash: f44fe0e66e5dd219606b2ceaa3860e01164ccfa4
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/09/2020
ms.locfileid: "44666255"
---
# <a name="authentication-in-microsoft-teams-rooms"></a>Microsoft 團隊聊天室中的驗證

Microsoft 團隊會議室裝置的帳戶管理是在應用程式層級處理。 應用程式會連線至 Microsoft 團隊、商務用 Skype 和 Exchange，以取得房間帳戶的資源，以啟用通話和會議體驗。 裝置會保持不限帳戶，以允許永不使用的功能、呼叫案例（適用于使用通話方案設定的裝置），以及在這些裝置上執行的自訂鎖定機制。 這表示這些裝置的驗證與終端使用者裝置的使用方式不同。  

針對使用 microsoft 365 或 Office 365 的 Microsoft 團隊聊天室裝置的所有客戶，建議進行新式驗證。 如果您有 Exchange server 或商務用 Skype server 的內部部署，請將混合式[新式驗證](https://docs.microsoft.com/office365/enterprise/hybrid-modern-auth-overview)與 Azure Active Directory （Azure AD）設定為使用新式驗證。

Microsoft 團隊聊天室版本4.4.25.0 及更新版本支援新式驗證。

## <a name="modern-authentication"></a>新式驗證

當您將新式驗證與 Microsoft 團隊聊天室應用程式搭配使用時，Active Directory 驗證庫（ADAL）是用來連線至 Microsoft 團隊、Exchange 和商務用 Skype。 Microsoft 團隊聊天室裝置是共用的裝置，會執行夜間重新開機，以確保順利運作，並取得重要的作業系統、驅動程式、固件或應用程式更新。 新式驗證機制在 OAuth 2.0 中使用[資源擁有者密碼身分](https://tools.ietf.org/html/rfc6749#section-1.3.3)驗證授權類型（不需要任何使用者干預）。 這是與 Microsoft 團隊聊天室應用程式所使用之資源帳戶相比，新式驗證運作方式的主要差異之一。 因此，Microsoft 團隊機房資源帳戶不應設定為使用多重要素驗證（MFA）、智慧卡驗證或用戶端憑證驗證（這些都可供最終使用者使用）。

現代驗證在 Microsoft 團隊會議室裝置和終端使用者裝置上的運作方式，是您無法使用資源帳戶來套用裝置層級設定的條件存取原則，例如「需要裝置標示合規性」或「需要混合式 Azure AD 已加入裝置」等。 這是因為裝置層級概念不適用於應用程式層級的新式驗證。 相反地，您可以在 Microsoft Intune 中註冊裝置，並使用透過[Intune 管理團隊](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)會議室中所提供的指導方針來套用合規性原則。

## <a name="enable-modern-authentication-on-a-microsoft-teams-rooms-device"></a>在 Microsoft 團隊聊天室裝置上啟用新式驗證

針對 Microsoft 團隊聊天室，若要在商務用 Skype 和 Exchange 中使用新式驗證，請在 Microsoft 團隊聊天室裝置上啟用新式驗證的用戶端設定。 您可以在 [裝置設定] 或 XML 設定檔中執行此動作。

> [!NOTE]
> 在您啟用新式驗證的用戶端設定之前，請確定您的環境已正確設定為使用新式驗證。

### <a name="using-device-settings"></a>使用裝置設定

1. 在 Microsoft 團隊聊天室裝置上，移至 [**更多**] （**...**）。
    
2. 選取 [**設定**]，然後輸入裝置管理員的使用者名稱和密碼。
3. 移至 [**帳戶**] 索引標籤，開啟 [**新式驗證**]，然後選取 [**儲存並**結束]。

### <a name="using-the-xml-config-file"></a>使用 XML 設定檔

在您的 SkypeSettings 檔案中，將新式驗證 XML 元素設定為**True**，如下所示。

```
<ModernAuthEnabled>True</ModernAuthEnabled>
```

若要套用設定，請參閱[使用 XML 設定檔遠端系統管理 Microsoft 球隊聊天室主控台設定](xml-config-file.md)。

## <a name="prepare-your-environment-for-modern-authentication"></a>針對新式驗證準備您的環境

開始之前，請確定您已瞭解搭配 Office 365 和 Azure AD 使用的身分識別模型。 您可以在[Office 365 身分識別模型與 Azure Active Directory](https://docs.microsoft.com/Office365/Enterprise/about-office-365-identity) ，以及[Microsoft 365 或 Office 365 的混合式身分識別和目錄同步](https://docs.microsoft.com/Office365/Enterprise/plan-for-directory-synchronization)處理中，找到更多相關資訊。

### <a name="enable-modern-authentication-in-microsoft-365-or-office-365"></a>在 Microsoft 365 或 Office 365 中啟用新式驗證

若要開啟 Exchange Online 的新式驗證，請參閱[啟用 Exchange online 中的新式驗證](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)。 如果您使用商務用 Skype Online，您也應該確認已針對商務用 Skype Online 開啟新式驗證。 若要深入瞭解，請參閱[商務用 Skype Online：針對新式驗證啟用您的租使用者](https://aka.ms/SkypeModernAuth)。

我們建議您不要移除 Exchange Online 的基本驗證原則，或停用您租使用者的基本驗證原則，然後再驗證 Microsoft 團隊會議室裝置在新式驗證設定為開啟且沒有已設定為使用基本驗證的裝置時，能成功登入 Exchange Online 與團隊或商務用 Skype Online。

如需在 Exchange Online 中停用基本驗證的詳細資訊，請參閱[停用 Exchange online 中的基本驗證](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)。

## <a name="hybrid-modern-authentication"></a>混合式新式驗證

若要確保成功驗證您的內部部署 Exchange server 和/或商務用 Skype server，您必須確認與 Microsoft 團隊聊天室搭配使用的資源帳戶已設定為從 Azure AD 取得授權。 若要深入瞭解適用于貴組織的混合式身分識別與方法，請閱讀下列主題： 

- [何謂密碼雜湊同步處理？](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-phs)
- [何謂 [直通驗證]？](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta)
- [何謂同盟？](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-fed)

### <a name="prerequisites-specific-to-microsoft-teams-rooms"></a>Microsoft 團隊聊天室專用的先決條件

在混合式拓朴中啟用新式驗證的先決條件，涵蓋[混合式新式驗證概述與使用內部部署商務用 Skype 和 Exchange 伺服器的先決條件](https://docs.microsoft.com/office365/enterprise/hybrid-modern-auth-overview)。 本文中所述的所有先決條件都是適用的。

不過，因為 Microsoft 團隊聊天室會使用[資源擁有者密碼](https://tools.ietf.org/html/rfc6749#section-1.3.3)認證授權，以及適用于新式驗證的基礎 REST api，所以以下是針對 Microsoft 團隊聊天室所特有的重要差異。

- 您必須有 Exchange Server 2016 CU8 或更新版本，或是 Exchange Server 2019 CU1 或更新版本。
- 您必須擁有商務用 Skype Server 2015 CU5 或更新版本，或是商務用 Skype Server 2019 或更新版本。
- 不論您有何種拓撲，都不支援 MFA。
- 如果您使用的是 Azure AD 支援的協力廠商驗證提供者，則它必須支援 OAuth 並使用資源擁有者密碼認證授權。
- 請勿針對使用應用程式設定的資源帳戶使用裝置層級設定的條件式存取原則。 這樣做會導致登入失敗。 請改為在 Microsoft Intune 中註冊裝置，並使用在[使用 Intune 管理團隊](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)會議室中發佈的指導方針來套用合規性原則。

### <a name="configure-exchange-server"></a>設定 Exchange Server

若要在 Exchange Server 中啟用混合式新式驗證，請參閱[如何將 Exchange Server 內部部署設定為使用混合式新式驗證](https://docs.microsoft.com/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)。

### <a name="configure-skype-for-business-server"></a>設定商務用 Skype Server

若要在商務用 Skype Server 上啟用混合式新式驗證，請參閱[如何將商務用 skype 內部部署設定為使用混合式新式驗證](https://docs.microsoft.com/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)。

### <a name="remove-or-disable-skype-for-business-and-exchange"></a>移除或停用商務用 Skype 和 Exchange

如果您的設定不允許混合式新式驗證，或者您需要移除或停用 Exchange 或商務用 Skype 的混合式新式驗證，請參閱[移除或停用商務用 skype 和 Exchange 中的混合式新式驗證](https://docs.microsoft.com/Office365/Enterprise/remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha)。

### <a name="azure-ad-conditional-access"></a>Azure AD 條件式存取

您可以針對 IP/位置式存取，設定與 Microsoft 團隊聊天室搭配使用的資源帳戶。 若要深入瞭解，請參閱[條件式存取：依位置封鎖存取](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-location)。

不支援其他條件式存取原則。 如需裝置合規性的詳細資訊，請參閱[使用 Intune 管理團隊會議室](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)。  
