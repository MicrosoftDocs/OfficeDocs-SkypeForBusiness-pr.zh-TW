---
title: 設定 [雲端語音信箱]
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
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
description: 瞭解如何為使用者設定雲端語音信箱。
ms.openlocfilehash: 9d6752098ff9dee6294d53fb24f6b7df6ee8e21c
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/05/2022
ms.locfileid: "66616249"
---
# <a name="set-up-cloud-voicemail"></a>設定 [雲端語音信箱]

本文適用于想要為使用者設定雲端語音信箱的 Microsoft 365 系統管理員。

雲端語音信箱在使用者的 Exchange 信箱中存入語音信箱訊息。 雲端語音信箱不支援協力廠商電子郵件系統。 如需Exchange Online授權需求，請參[閱Exchange Online服務說明](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description#features-available-to-all-plans)。 如需系統管理員角色的詳細資訊，請參閱 [關於系統管理員角色](/microsoft-365/admin/add-users/about-admin-roles)。

## <a name="cloud-voicemail-provisioning"></a>雲端語音信箱布建

對於 Teams 使用者，系統會自動設定和布建雲端語音信箱。 *雲端語音信箱不需要Microsoft Teams 電話授權。*

Teams 使用者的布建與商務用 Skype Online 使用者的布建並不相同。 對於商務用 Skype Online 使用者，當使用者獲派電話系統授權並企業語音布建系統啟用時，系統會自動設定和布建雲端語音信箱。

對於商務用 Skype Server內部部署使用者，系統會自動設定和布建雲端語音信箱。 不過，您必須設定商務用 Skype Server環境，才能將通話路由至雲端語音信箱。 如需詳細資訊，請參閱[規劃內部部署使用者雲端語音信箱服務](/skypeforbusiness/hybrid/plan-cloud-voicemail)。

## <a name="cloud-voicemail-storage"></a>雲端語音信箱儲存空間

由雲端語音信箱產生的語音信箱訊息會傳送並儲存在使用者的 Exchange 信箱中，不限於Exchange Online或Exchange Server。 語音信箱沒有特定或額外的儲存空間。 存取語音信箱的用戶端 (例如 Microsoft Outlook、Microsoft Teams 或 商務用 Skype) 透過 Exchange 信箱和提供的 API 來存取。

語音信箱訊息包含附加的音訊檔案，其中包含語音訊息，以及啟用) 時 (語音信箱轉譯。

使用者的 Exchange 信箱會儲存任何自訂的錄製問候語。 雲端語音信箱在來電期間視需要擷取這些問候語。

## <a name="cloud-voicemail-processing"></a>雲端語音信箱處理

雲端語音信箱的錄製和轉譯是從 Microsoft 365 開始，從路由至雲端語音信箱的通話來源開始。 郵件隨即傳送至使用者的 Exchange 信箱。

例如，如果無法透過會話框線控制器直接路由使用者撥打電話， (歐洲的 SBC) ，則會在歐洲執行語音信箱錄製和轉譯。 郵件隨即傳送至使用者的 Exchange 信箱。 另一個範例是，假設 Teams 使用者在北美洲呼叫歐洲地區無法使用的 Teams 使用者。 在此情況下，通話會在北美洲啟動，處理會在 北美洲 中進行，然後語音信箱會傳送到歐洲的使用者 Exchange 信箱。

語音信箱的傳遞方式是使用簡易郵件傳輸通訊協定 (SMTP) 任何其他電子郵件一樣。

## <a name="manage-cloud-voicemail-for-users"></a>管理使用者雲端語音信箱

您可以指定語音信箱原則並設定語音信箱設定，以管理使用者的雲端語音信箱。  

- **語音信箱原則** 可讓您管理使用者群組的功能。 您可以針對通話接聽規則、語音信箱轉譯、轉譯不雅用遮罩、轉譯翻譯和系統提示語言等功能，設定並指派現有或新的語音信箱原則。 如需管理語音信箱原則的相關資訊，請參閱 [管理語音信箱原則](manage-voicemail-policies.md)。

- **語音信箱設定** 可讓您為個別使用者設定設定。 您可以設定例如通話接聽規則、提示語言、語音轉換預設文字和休假問候語等設定。 如需為個別使用者設定設定的相關資訊，請參閱 [管理語音信箱設定](manage-voicemail-settings.md)。 請注意，您的使用者也可以在 Teams 用戶端中設定這些設定，方法是移至 [ **設定] -> [通話] -> [設定語音信箱]**。

## <a name="control-routing-of-calls-to-cloud-voicemail"></a>控制來電傳送到雲端語音信箱

為雲端語音信箱布建之所有使用者的預設設定是允許將通話轉接至雲端語音信箱，並允許使用者將來電轉接至雲端語音信箱。

您可以使用 Teams 系統管理中心或使用 PowerShell 來控制 Teams 使用者是否允許轉接來電至雲端語音信箱。 

- 若要使用 Teams 系統管理中心，請移至 **語音**  ->  **通話原則**->新增或編輯現有原則 ->**可以使用語音信箱路由輸入通話**。  

- 在 PowerShell 中，使用 Set-CsTeamsCallingPolicy Cmdlet 搭配 AllowVoicemail 參數。 如需詳細資訊，請參閱 [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)。

  - 如果您將 AllowVoicemail 設為 AlwaysDisabled，無論使用者的來電轉接或未接聽設定為何，通話永遠不會路由到語音信箱。 在 Teams 中，語音信箱無法做為來電轉接或未接聽的設定。

  - 如果您將 AllowVoicemail 設為 AlwaysEnabled，通話一律會轉接至語音信箱，在鈴聲三十秒之後未接聽，不論使用者未接聽的來電轉接設定為何。

  - 如果您將 AllowVoicemail 設為 UserOverride，呼叫會根據使用者的來電轉接和/或未接聽的設定轉接至語音信箱。

## <a name="set-up-cloud-voicemail-to-work-with-on-premises-users"></a>設定雲端語音信箱以與內部部署使用者合作

您可以使用 雲端語音信箱，為在 Exchange Server 上擁有信箱的使用者或使用商務用 Skype Server的使用者提供語音信箱功能。

本節說明如何為Exchange Server信箱使用者設定雲端語音信箱。 如需如何為商務用 Skype Server使用者設定雲端語音信箱的相關資訊，請參閱[規劃內部部署使用者雲端語音信箱服務](/skypeforbusiness/hybrid/plan-cloud-voicemail)。

### <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>為Exchange Server信箱使用者設定雲端語音信箱

下列資訊是關於設定雲端語音信箱，以與在 Exchange Server 上擁有信箱的 Teams 使用者合作。

1. 語音信箱訊息會透過 SMTP 透過Exchange Online Protection傳送至使用者的 Exchange 信箱。 若要成功傳遞這些郵件，請確定 Exchange 伺服器和 Exchange Online Protection 之間已正確設定 Exchange 連接器。 如需詳細資訊，請參閱 [使用連接器來設定郵件流程](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。

2. 若要啟用語音信箱功能，例如在 Teams 用戶端中自訂問候語和視覺化語音信箱，您必須設定 Microsoft 365 和Exchange Server信箱之間的連線。 若要啟用此連線，您必須設定新 Exchange Oauth 驗證通訊協定，詳述于設定[Exchange 與Exchange Online組織之間的 OAuth 驗證](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)，或從 Exchange 2013 CU5 或更新版本執行 Exchange 混合式精靈。 您也必須設定 Teams 與 Exchange Server 之間的整合與 Oauth，詳述請參閱在[Teams 與 Exchange Server 之間設定整合和 OAuth](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)。

## <a name="enable-protected-voicemail-in-your-organization"></a>在貴組織中啟用受保護的語音信箱

當某人為貴組織中的使用者留下語音信箱訊息時，語音信箱會以電子郵件附件的形式傳送到使用者的信箱。

使用Microsoft Purview 資訊保護，您可以加密內部和外部來電者留下的語音信箱訊息。 您也可以防止使用者轉寄這些訊息。 擁有Exchange Online信箱的使用者支援此功能。

若要加密語音信箱訊息，您可以建立敏感度標籤。 透過自動標籤功能，您可以確保標籤會自動套用至內送語音信箱訊息。

當您啟用受保護的語音信箱時，使用者可以在 Outlook、Outlook 網頁版或 Android 或 iOS 版 Outlook 中開啟郵件，以聆聽受保護的語音信箱訊息。 Microsoft Teams 或 商務用 Skype 無法開啟受保護的語音信箱訊息。

若要建立語音信箱的敏感度標籤，請參 [閱使用敏感度標籤](/microsoft-365/compliance/encryption-sensitivity-labels#let-users-assign-permissions)。 在 [ **加密] 區** 段中，選擇 **[允許使用者在套用標籤時指派許可權]**。 選 **取 [在 Outlook 中，強制執行下列其中一項限制**]，然後選取 [ **不要轉寄** ] 選項。

若要建立自動標籤原則以將敏感度標籤套用至語音信箱，請參閱 [如何設定自動標籤原則](/microsoft-365/compliance/apply-sensitivity-label-automatically#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange)，並指定下列特定設定：

- 如 **需選擇您要套用此標籤的資訊**，請選取 **[自訂原則]**。

- 針對 **[選擇您要套用標籤的位置**]，選取 [ **位置：所有使用者的 Exchange]**。

- 若  **要設定一般或進階規則**，請選取 [ **進階規則]**。

- Exchange 規則：
  - 條件：
    - **頁首符合模式**：Content-Class = Voice-CA
    - **寄件者的 IP 位址是**：13.107.64.0/18， 52.112.0.0/14、52.120.0.0/14、52.238.119.141/32、52.244.160.207/32

- 若 **要選擇要自動套用的標籤**，請選取您在上述步驟中為語音信箱建立的敏感度標籤。

- 如 **需電子郵件的其他設定**，請選取 [將 **加密套用到組織外部接收的電子郵件**]，然後指定版權管理擁有者。

[寄件者 IP 位址] 中指定的 IP V4 範圍，是根據識別碼 12 中的清單[，以Office 365 URL 和 IP 位址範圍為依據](/microsoft-365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)。

如需郵件加密的詳細資訊，請參閱 [定義郵件流程規則以加密電子郵件訊息](/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)。

## <a name="help-your-users-learn-about-cloud-voicemail-features"></a>協助使用者瞭解雲端語音信箱功能

若要協助使用者瞭解如何使用和管理雲端語音信箱功能，您可以建議使用下列文章：

- [在 Teams 中檢查您的語音信箱](https://support.microsoft.com/office/check-your-voicemail-in-teams-f8d568ce-7329-4fe2-a6a2-325ec2e2b419)
- [管理 Teams 中的通話設定](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)
