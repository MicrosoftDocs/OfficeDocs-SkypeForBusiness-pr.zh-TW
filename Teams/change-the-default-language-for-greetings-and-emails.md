---
title: 變更問候語和電子郵件的預設語言
author: crowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: 820c3892-1b7e-47d3-ae8d-6e27e7cbcf38
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: 瞭解如何設定 Microsoft Teams 和商務用 Skype，為貴組織的預設語音信箱問候語使用其他語言。
ms.openlocfilehash: 30e122c0d41c93326cdfa39de4c0ceb3a6d55cd2
ms.sourcegitcommit: f2253162a23d0683e7424211da1a0a8760c8a91b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/29/2022
ms.locfileid: "66241122"
---
# <a name="change-the-default-language-for-greetings-and-emails"></a>變更問候語和電子郵件的預設語言

雲端語音信箱使用各種語言設定來播放問候語、產生轉譯，以及產生語音信箱訊息。 根據預設，您可以在租使用者層級、原則或特定使用者上個別指定語言設定。

## <a name="greetings"></a>問候
問候語會播放給離開語音信箱的來電者，而且可以是下列類型：

- 系統問候語
- 使用者所錄製的自訂問候語
- 在使用者上指定的自訂文字轉換語音問候語

用來播放系統問候語的語言會依優先順序排列，例如指派給使用者的線上語音信箱原則中指定的主要和次要提示語言、為使用者指定的慣用語言，或預設的租使用者語言。

自訂和不在辦公室問候語是由使用者以使用者選擇的語言錄製。

如果使用者或租使用者系統管理員為使用者指定自訂文字轉換語音問候語，產生語音所用的語言就是與文字轉換語音問候語一起指定的 PromptLanguage。

只有當使用者未錄製自訂問候語時，才會使用自訂文字轉換語音問候語。

## <a name="transcription"></a>轉錄
如果線上語音信箱原則為來電使用者啟用，雲端語音信箱會嘗試轉譯來電者留下的語音信箱。 它會使用語音偵測來瞭解音訊內容中使用的語言，並且盡可能使用偵測到的語言來轉譯內容。

## <a name="transcription-translation"></a>轉譯轉譯
如果線上語音信箱原則為來電使用者啟用，雲端語音信箱會翻譯轉譯的語音信箱。 它會依優先順序將語音偵測期間偵測到的語言翻譯成使用者所指定的慣用語言或預設的租使用者語言。

## <a name="voicemail-message-template"></a>語音信箱訊息範本
雲端語音信箱會根據使用者所指定的慣用語言或預設租使用者語言，以優先順序順序，使用語言範本產生語音信箱訊息。

## <a name="setting-the-preferred-language-for-a-user"></a>設定使用者的慣用語言
您可以在 Azure Active Directory 或 內部部署的 Active Directory 中，為使用 PowerShell 的使用者設定慣用語言。 如需詳細資訊，請參閱[如何設定 Microsoft 365 或 Office 365 的語言和地區設定](/office365/troubleshoot/access-management/set-language-and-region)。

使用者可以在登入之後，透過他們的設定來變更自己的慣用語言。 如需詳細資訊，請參閱 [變更商務用 Microsoft 365 中的顯示語言和時區](https://support.office.com/article/change-your-display-language-and-time-zone-in-microsoft-365-for-business-6f238bff-5252-441e-b32b-655d5d85d15b?ui=en-US&rs=en-US&ad=US)

## <a name="change-the-system-language-for-everyone-in-your-organization"></a>變更貴組織中每個人的系統語言

1. 使用您的[全域系統管理員](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)帳戶登入。 [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home)

2. 在 [Microsoft 365 系統管理中心] 中，選擇 [**設定**  >  **組織設定**  >  **組織設定檔]**。

3. 選擇 **[組織資訊]**。

4. 從 [ **慣用語言** ] 清單中為組織中的每個人選取語言。

5. 選擇 [ **儲存]**。

**您可用的語言取決於組織的位置**。 例如，如果您的組織位於美國，您可以將預設語言設定為英文或西班牙文。 如果您的組織位於加拿大，您可以選擇英文和法文。

## <a name="supported-languages-in-cloud-voicemail"></a>雲端語音信箱支援的語言
如需 Microsoft Teams 和 商務用 Skype 雲端語音信箱 支援語言的清單，請參閱[雲端語音信箱支援的語言](languages-for-voicemail-greetings-and-messages.md)。
  

## <a name="custom-greeting-recorded-by-a-user"></a>使用者錄製的自訂問候語
使用者可以錄製自己的自訂和不在辦公室自訂問候語。 請參閱[Teams 桌面用戶端設定](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)和[檢查商務用 Skype語音信箱和選項](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)。

## <a name="custom-text-to-speech-greeting-specified-for-a-user"></a>為使用者指定的自訂文字轉換語音問候語
租使用者系統管理員可以使用 Teams 系統管理中心使用者詳細資料頁面上的 [語音信箱] 索引標籤，或使用 [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings) Cmdlet，為使用者指定自訂文字轉換語音問候語和提示語言。

## <a name="custom-text-to-speech-greeting-specified-by-a-user"></a>使用者指定的自訂文字轉換語音問候語
使用者可以指定自己的自訂文字轉換語音問候語，以及用於問候語的語言。 針對 Microsoft Teams - 使用者可以從 [Teams 桌面用戶端設定](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)變更他們的語音信箱問候語。 針對商務用 Skype ， [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail) 然後在 [提示語言] 底下選擇新的 **語言**。 


## <a name="related-articles"></a>相關文章

[Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings)

[Get-CsOnlineVoicemailUserSettings](/powershell/module/skype/get-csonlinevoicemailusersettings)

[Set-CsOnlineVoicemailPolicy](/powershell/module/skype/set-csonlinevoicemailpolicy)

[Get-CsOnlineVoicemailPolicy](/powershell/module/skype/get-csonlinevoicemailpolicy)
