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
description: 瞭解如何為使用者雲端語音信箱帳戶。
ms.openlocfilehash: f1645ec9a14a5b201809cbe12219d7b1e437d355
ms.sourcegitcommit: edf68b7ac4f1861259a0990157ee6ae84f68ca42
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2022
ms.locfileid: "62974470"
---
# <a name="set-up-cloud-voicemail"></a>設定 [雲端語音信箱]

本文適用于Microsoft 365使用者設定雲端語音信箱管理員。 

雲端語音信箱將語音信箱訊息存到使用者的信箱Exchange訊息。 雲端語音信箱不支援協力廠商電子郵件系統。 有關Exchange Online需求，請參閱Exchange Online[描述](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description#features-available-to-all-plans)。 有關系統管理員角色的資訊，請參閱 [關於系統管理員角色](/microsoft-365/admin/add-users/about-admin-roles)。

## <a name="cloud-voicemail-provisioning"></a>雲端語音信箱資源調配

針對Teams，系統會自動雲端語音信箱設定和設定使用者。 *系統Microsoft Teams 電話授權雲端語音信箱。*

針對使用者Teams與適用于線上使用者商務用 Skype相同。 針對 商務用 Skype Online 使用者，雲端語音信箱使用者獲得 電話系統 授權，且已由企業語音系統啟用時，系統會自動設定和設定使用者。

針對商務用 Skype Server內部部署使用者，系統會自動雲端語音信箱設定和設定。 不過，您必須設定商務用 Skype Server，將通話路由到雲端語音信箱。 詳細資訊請參閱為內部[雲端語音信箱使用者規劃服務](/skypeforbusiness/hybrid/plan-cloud-voicemail.md)。 

## <a name="cloud-voicemail-storage"></a>雲端語音信箱儲存空間

使用者產生的語音雲端語音信箱訊息會傳送到使用者的信箱，並儲存在Exchange信箱中，Exchange Online或Exchange Server。 語音信箱沒有特定或額外的儲存空間。 存取語音信箱的用戶端 (例如 Microsoft Outlook、Microsoft Teams或 商務用 Skype) 透過 Exchange 信箱和提供的 API 執行此作業。 

語音信箱訊息包含附加的音訊檔案，內含語音信箱訊息，如果已啟用語音信箱 (語音信箱) 。 

使用者Exchange信箱會儲存任何自訂錄製的問候語。 這些問候語會雲端語音信箱來電期間，由來電者所取。 

## <a name="cloud-voicemail-processing"></a>雲端語音信箱處理 

錄製和錄製雲端語音信箱是從Microsoft 365路由至該電話的起始雲端語音信箱。 郵件隨即傳送到使用者的信箱Exchange信箱。 

例如，如果通話透過會話邊界控制器 (SBC) 進入無法使用的直接路由使用者，則語音信箱錄製和語音信箱錄音和文字翻譯會在歐洲完成。 郵件隨即傳送到使用者的信箱Exchange信箱。 另一個範例是，假設Teams北美地區的使用者呼叫歐洲Teams無法使用的使用者。 在此案例中，通話會在北美開始，處理會在北美進行，然後語音信箱會傳送到使用者的歐洲Exchange信箱。 

語音信箱的傳送Exchange使用簡易郵件傳輸通訊協定 (SMTP) ，就像任何其他電子郵件一樣。 

## <a name="manage-cloud-voicemail-for-users"></a>管理雲端語音信箱使用者使用 

若要管理雲端語音信箱使用者使用的功能，請使用 Teams PowerShell 模組，如下所示。 

若要管理雲端語音信箱群組的新功能，請使用[New-CsOnlineVoicemailPolicy](/powershell/module/skype/new-csonlinevoicemailpolicy) Cmdlet。 您可以設定及指派現有或新的語音信箱原則，以使用通話接聽規則、語音信箱語音應答、文字翻譯不規範遮罩、文字翻譯及系統提示語言等功能。 詳細資訊，請參閱 [New-CsOnlineVoicemailPolicy](/powershell/module/skype/new-csonlinevoicemailpolicy)。

若要管理雲端語音信箱的使用者設定，請使用[Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings) Cmdlet。 雲端語音信箱可適用于個別使用者的設定包括通話接聽規則、提示語言、預設語音文字，以及假期問候語。 詳細資訊，請參閱 [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings)。
 (Teams  ->  請注意，您的使用者也可以使用 **CallsConfigure**  ->  語音信箱設定在用戶端中設定這些) ****

您也可以 雲端語音信箱使用[Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings) Cmdlet，將 VoicemailEnabled 參數設定為 $false。 此設定可確保雲端語音信箱使用者無法再錄製語音信箱。



## <a name="control-routing-of-calls-to-cloud-voicemail"></a>控制呼叫路由至雲端語音信箱 

為 雲端語音信箱 所設定之所有使用者的預設設定是允許將通話路由至 雲端語音信箱，以及允許使用者將通話轉雲端語音信箱。 

您可以使用 Cmdlet 與 AllowVoicemail 參數雲端語音信箱 Cmdlet，Teams Set-CsTeamsCallingPolicy使用者是否允許將通話路由至其他使用者。 詳細資訊，請參閱 [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy.md)。 

- 如果您將 AllowVoicemail 設為 AlwaysDisabled，來電永遠不會路由至語音信箱，無論使用者的呼叫轉寄或未接聽設定。 語音信箱無法以呼叫轉轉或未Teams。  

- 如果您將 AllowVoicemail 設為 AlwaysEnabled，來電在響鈴 30 秒之後，一直會轉寄到未接聽的語音信箱 ，無論使用者的呼叫轉寄設定如何。  

- 如果您將 AllowVoicemail 設定為 UserOverride，通話會根據使用者的呼叫轉寄和/或未接聽設定，轉寄到語音信箱。 



## <a name="set-up-cloud-voicemail-to-work-with-on-premises-users"></a>設定雲端語音信箱內部部署使用者

您可以使用 雲端語音信箱，為在 Exchange 伺服器上擁有信箱的使用者，或正在使用信箱的使用者提供語音信箱商務用 Skype Server。 

本節說明如何為信箱使用者雲端語音信箱Exchange Server使用者。 若要瞭解如何為雲端語音信箱使用者商務用 Skype Server，請參閱規劃雲端語音信箱使用者[的服務](/skypeforbusiness/hybrid/plan-cloud-voicemail)。

### <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>設定雲端語音信箱信箱Exchange Server的使用者

下列資訊說明如何雲端語音信箱使用Teams信箱的使用者Exchange Server。

1. 語音信箱訊息會透過透過 Exchange 路由的 SMTP 傳送到使用者的信箱Exchange Online Protection。 若要成功傳遞這些郵件，請確定 Exchange 伺服器與伺服器之間正確Exchange連接器Exchange Online Protection。 詳細資訊，請參閱使用[連接器設定郵件Flow](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。

2. 若要啟用語音信箱功能，例如自訂 Teams 中的問候語和視覺語音信箱，您必須設定 Microsoft 365 與 Exchange Server 之間的連接。 若要啟用此連接，您必須設定 Exchange 與 Exchange Online 組織之間設定[OAuth](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)驗證中所述的新 Exchange 的致法驗證通訊協定，或執行 Exchange 2013 CU5 或更大的 Exchange 混合式精靈。 您也必須在 Teams 和 Exchange Server之間設定整合和[OAuth Teams 和 oAuth](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises) Exchange Server。


## <a name="enable-protected-voicemail-in-your-organization"></a>在貴組織中啟用受保護的語音信箱

當某人為貴組織的使用者留下語音信箱訊息時，語音信箱會以電子郵件訊息附件形式傳送到使用者的信箱。 您可以使用郵件流程規則來申請郵件加密，以防止這些語音信箱訊息轉寄給其他收件者。 當您啟用受保護的語音信箱時，使用者可以撥打到語音信箱，或在 Outlook、Outlook 網頁版 或 android 或 iOS Outlook 中開啟郵件，來聆聽受保護的語音信箱訊息。 受保護的語音信箱訊息無法于 商務用 Skype 或 Microsoft Teams。

若要進一步瞭解有關郵件加密的資訊，請參閱定義郵件 [流程規則以加密電子郵件訊息](/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)。



## <a name="help-your-users-learn-about-cloud-voicemail-features"></a>協助使用者瞭解雲端語音信箱功能

若要協助使用者瞭解如何使用及管理雲端語音信箱，您可以建議下列文章： 

- [檢查語音信箱Teams](https://support.microsoft.com/office/check-your-voicemail-in-teams-f8d568ce-7329-4fe2-a6a2-325ec2e2b419)
- [在 Teams](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)
