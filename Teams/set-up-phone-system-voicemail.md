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
description: 瞭解如何為使用者雲端語音信箱帳戶。
ms.openlocfilehash: f448ba79c2451383c0ca85916309bdfab3b69a96
ms.sourcegitcommit: 279ab5236431961c5181e2c01a69e5aa4290d381
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2021
ms.locfileid: "60462367"
---
# <a name="set-up-cloud-voicemail"></a>設定 [雲端語音信箱]

本文適用于Microsoft 365或Office 365系統管理員，如想要為企業雲端語音信箱設定 雲端語音信箱 管理員角色[](/microsoft-365/admin/add-users/about-admin-roles)中所述。 雲端語音信箱需要Exchange信箱來存下語音信箱訊息的使用者。 它不支援協力廠商電子郵件系統。

## <a name="cloud-voicemail-for-teams-users"></a>雲端語音信箱使用者Teams

針對Teams，系統雲端語音信箱自動設定和設定。 您Microsoft Teams 電話授權就不需要雲端語音信箱。

## <a name="help-your-users-learn-teams-voicemail-features"></a>協助使用者瞭解Teams語音信箱功能

我們有下列資訊可讓使用者在使用及管理語音信箱Teams：

- [檢查語音信箱Teams](https://support.microsoft.com/office/check-your-voicemail-in-teams-f8d568ce-7329-4fe2-a6a2-325ec2e2b419)
- [在 Teams](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)

## <a name="setting-up-cloud-voicemail-to-work-with-on-premises-users"></a>設定雲端語音信箱內部部署使用者

您可以使用雲端語音信箱功能，為在 Exchange 伺服器上擁有信箱的使用者，或為使用商務用 Skype Server。 本節提供這些案例的資訊。 

### <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>設定雲端語音信箱信箱Exchange Server使用者

下列資訊說明如何雲端語音信箱使用Microsoft Teams 電話信箱的使用者Exchange Server。

1. 語音信箱訊息會透過透過 Exchange 路由至使用者的信箱Exchange Online Protection。 若要成功傳遞這些郵件，請務必在伺服器Exchange伺服器與伺服器之間正確Exchange連接器Exchange Online Protection;[使用連接器設定郵件Flow。](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)

2. 若要啟用語音信箱功能，例如自訂 商務用 Skype 用戶端中的問候語和視覺語音信箱，必須透過 Microsoft 365 或 Office 365 透過 Exchange Web Services 從 Exchange 伺服器信箱進行連接。 若要啟用此連接，您必須設定 Exchange 和 Exchange Online 組織之間設定[OAuth](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)驗證中所述的新 Exchange 的致法驗證通訊協定，或執行 Exchange 2013 CU5 或更大的 Exchange 混合式精靈。 此外，您必須在 商務用 Skype Online 和 Exchange 伺服器之間設定整合和小Exchange在 商務用 Skype Online 和 Exchange Server 之間[設定整合和 OAuth。](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)

### <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a>設定雲端語音信箱使用者商務用 Skype Server設定

若要設定商務用 Skype伺服器使用者雲端語音信箱，請參閱雲端語音信箱[部署使用者規劃服務](/skypeforbusiness/hybrid/plan-cloud-voicemail)。

## <a name="enabling-protected-voicemail-in-your-organization"></a>在貴組織中啟用受保護的語音信箱

當某人為貴組織的使用者留下語音信箱訊息時，語音信箱會以電子郵件訊息附件形式傳送到使用者的信箱。 使用郵件流程規則來適用郵件加密，您可以防止這些語音信箱訊息轉寄給其他收件者。 當您啟用受保護的語音信箱時，使用者可以在 android 或 iOS 版 Outlook、Outlook 網頁版 或 Outlook 中撥打語音信箱來聆聽受保護的語音信箱訊息。 受保護的語音信箱訊息無法于 商務用 Skype 或 Microsoft Teams。

若要進一步瞭解有關郵件加密的資訊，請參閱定義郵件 [流程規則以加密電子郵件訊息](/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)。
