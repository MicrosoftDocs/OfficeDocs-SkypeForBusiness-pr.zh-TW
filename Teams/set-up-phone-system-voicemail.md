---
title: 設定 [雲端語音信箱]
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: wasseemh, phans
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
description: 瞭解如何設定雲端語音信箱使用者。
ms.openlocfilehash: f4547d081cf7b0175da7222bf68fde97cecd21c9
ms.sourcegitcommit: d23185cf6caeeeb055c36609e7c788a2b2e8d07d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/15/2021
ms.locfileid: "60367505"
---
# <a name="set-up-cloud-voicemail"></a>設定 [雲端語音信箱]

本文適用于Microsoft 365或Office 365系統管理員，如想要為企業雲端語音信箱設定 雲端語音信箱管理員角色[](/microsoft-365/admin/add-users/about-admin-roles)中所述。

> [!NOTE]
> 雲端語音信箱只支援將語音信箱Exchange信箱中，且不支援任何協力廠商電子郵件系統。

> [!NOTE]
> 當代理人代表委派者接聽來電時，雲端語音信箱。 使用者可以接收未接來電的通知。

## <a name="cloud-voicemail-for-teams-users"></a>雲端語音信箱使用者Teams

針對Teams，系統會自動雲端語音信箱設定和設定使用者。 請注意，電話系統授權並不雲端語音信箱。

## <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>設定雲端語音信箱信箱Exchange Server使用者

下列資訊是有關將雲端語音信箱與線上的使用者共同作業電話系統但信箱位於Exchange Server。

1. 語音信箱訊息會透過透過 Exchange 路由至使用者的信箱Exchange Online Protection。 若要順利傳遞這些郵件，請確定已正確Exchange伺服器與伺服器之間正確Exchange連接器Exchange Online Protection;[使用連接器設定郵件Flow。](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)

2. 若要啟用語音信箱功能，例如自訂 商務用 Skype 用戶端中的問候語和視覺語音信箱，必須透過 Microsoft 365 web Services 從 Microsoft 365 或 Office 365 連接到 Exchange 伺服器信箱Exchange。 若要啟用此連接，您必須設定 Exchange 和 Exchange Online 組織之間設定[OAuth](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)驗證中所述的新 Exchange 的致法驗證通訊協定，或從 Exchange 2013 CU5 或更Exchange執行 Exchange 混合式精靈。 此外，您必須在 商務用 Skype Online 與 Exchange 伺服器之間設定整合和小Exchange在 商務用 Skype Online 和[Exchange Server。](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)

## <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a>設定 雲端語音信箱 使用者商務用 Skype Server設定

若要設定商務用 Skype伺服器使用者雲端語音信箱，請參閱規劃雲端語音信箱[內部部署使用者的服務](/skypeforbusiness/hybrid/plan-cloud-voicemail)。

## <a name="enabling-protected-voicemail-in-your-organization"></a>在貴組織中啟用受保護的語音信箱

當某人為貴組織的使用者留下語音信箱訊息時，語音信箱會以電子郵件訊息附件形式傳送到使用者的信箱。 使用郵件流程規則來適用郵件加密，您可以防止這些語音信箱訊息轉寄給其他收件者。 當您啟用受保護的語音信箱時，使用者可以在 android 或 iOS 版 Outlook、Outlook 網頁版 或 Outlook 中撥打語音信箱來聆聽受保護的語音信箱訊息。 受保護的語音信箱訊息無法商務用 Skype或Microsoft Teams。

有關郵件加密的資訊，請參閱 [電子郵件加密](/microsoft-365/compliance/email-encryption)。

> [!NOTE]
> 只有當通話來自內部使用者時，我們才將加密功能適用于語音信箱。 如果來電來自外部使用者，語音信箱將不會加密。

若要設定受保護的語音信箱，請執行下列操作：

1. 使用具有全域系統管理員許可權的帳戶 <https://admin.microsoft.com> 前往並登錄。
2. 選取 **顯示全部**，然後前往系統管理  >  **中心Exchange。**
3. 在系統管理Exchange，選取 **郵件流程**  >  **規則**。
4. 選取 **+** **新增**，然後選取 **Office 365 郵件加密郵件的許可權保護**。
5. 提供新郵件流程規則的名稱，然後在下列的下列條件中選取郵件屬性 ：包括語音  >   \> **信箱的郵件類型**。 選取 **確定**。
6. 在 **執行下列操作下**，選取 Office 365 郵件加密郵件的適用許可權保護，然後選取選取 **其中一個**。 在 **RMS 範本下**，選取 請勿 **轉出**。 選取 **確定** ，然後 **儲存**。

    > [!NOTE]
    > 如果 **RMS 範本** 清單是空的，您必須設定郵件加密。 有關設定郵件加密的資訊，請參閱下列文章：
    >
    > - [設定新的郵件加密功能](/microsoft-365/compliance/set-up-new-message-encryption-capabilities)
    > - [建立及管理 Azure 資訊保護的範本](/information-protection/deploy-use/configure-policy-templates)
    > - [電子郵件的請勿轉轉選項](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)

    > [!NOTE]
    > 您需要為想要顯示語音信箱表單的使用者、企業及組織設定下列登錄機機密鑰：[HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Outlook\Addins] "AllowVoicemailForm"=dword：00000001

## <a name="help-your-users-learn-teams-voicemail-features"></a>協助使用者瞭解Teams語音信箱功能

我們有下列資訊可讓使用者管理語音信箱設定，以及其他通話Teams：

- [在 中管理您的通話Teams。](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f) 本文說明如何管理所有使用者通話Teams功能。

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a>協助使用者瞭解商務用 Skype語音信箱功能

我們有訓練資訊和文章，可協助使用者成功使用語音信箱商務用 Skype語音信箱。 指向下列文章：

- 檢查[商務用 Skype](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)和選項：本文說明如何在 商務用 Skype 中聆聽語音信箱、變更語音信箱問候語、變更語音信箱設定，以及以不同速度聆聽語音信箱。

- [商務用 Skype 2016 年訓練](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a>相關主題

[設定商務用 Skype Online](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[以下是可透過電話系統獲得的功能](here-s-what-you-get-with-phone-system.md)

[規劃商務用 Skype 和 Exchange Server 的先決條件的移轉](/SkypeForBusiness/hybrid/plan-um-migration)
