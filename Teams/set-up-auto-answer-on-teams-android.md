---
title: 設定Teams Android裝置的自動回應
author: mkbond007
ms.author: mabond
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: kponnus
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom: ''
description: 瞭解如何使用 PowerShell 在Android和Teams視訊手機裝置上設定Microsoft Teams 會議室的自動接聽功能。
ms.openlocfilehash: fac458a2b7b100a2074dbaac0e209fbdd3527eef
ms.sourcegitcommit: 9532eb79310cd653010565607fa394f2b8dd182d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/23/2022
ms.locfileid: "65646592"
---
# <a name="set-up-auto-answer-for-microsoft-teams-rooms-on-android-and-teams-video-phone-devices"></a>在Android和Teams視訊手機裝置上設定Microsoft Teams 會議室自動接聽

本文將協助您在Android和Teams視訊手機裝置上設定Microsoft Teams 會議室自動接聽功能。 自動接聽可讓您組織中具有系統管理許可權的人員變更其裝置設定，以自動接受傳入的會議邀請，並自動接受視訊通話。

## <a name="enable-auto-answer-with-powershell"></a>使用 PowerShell 啟用自動解答

使用下列屬性在Android和Teams視訊手機裝置上啟用Microsoft Teams 會議室自動解答：

- **Set-CsTeamsCallingPolicy -AutoAnswerEnabledType**
- **Set-CsTeamsIPPhonePolicy -SignInMode**

### <a name="1-turn-on-auto-answer-for-incoming-meeting-invites"></a>1. 開啟內送會議邀請的自動回復

您可以使用 **Set-CsTeamsCallingPolicy -AutoAnswerEnabledType** 為傳入的會議邀請開啟自動回復。 自動回答預設為 **關閉** 。 此原則僅適用于傳入的會議邀請，不支援其他通話類型。 如需 Cmdlet 的詳細資訊，請參閱 [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy) 。

```powershell
Set-CsTeamsCallingPolicy -AutoAnswerEnabledType Enabled
```

### <a name="2-set-the-device-sign-in-mode"></a>2. 設定裝置登入模式

您可以使用 **Set-CsTeamsIPPhonePolicy -SignInMode** 來設定裝置的登入模式，以判斷登入Teams時的行為。 如需 Cmdlet 的詳細資訊，請參閱 [Set-CsTeamsIPPhonePolicy](/powershell/module/skype/set-csteamsipphonepolicy) 。

登入模式有三個選項：

- **UserSignIn：** 在手機上啟用個別使用者Teams體驗。
- **CommonAreaPhoneSignIn：** 在手機上啟用常見的區域電話體驗。
- **MeetingSignIn：** 啟用電話上的會議室體驗。

例如，下列原則會將登入模式設定為會議室體驗。

```powershell
Set-CsTeamsIPPhonePolicy -Identity Device -SignInMode MeetingSignIn
```

### <a name="configure-device-settings"></a>設定裝置設定

啟用自動回答之後，具有系統管理許可權的使用者就可以在其裝置設定中開啟此功能。 若要在裝置層級啟用此功能，您必須開啟 **[自動接受傳入的會議邀請]**。 您也可以開啟 **[自動接受視訊]**。 這兩個設定預設為關閉。

## <a name="related-topics"></a>相關主題

[Microsoft 支援服務：通話和裝置](https://support.microsoft.com/office/calls-and-devices-4d96653e-6176-4978-98ab-2c19df137e43#ID0EBBD=Devices)

[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

[Set-CsTeamsIPPhonePolicy](/powershell/module/skype/set-csteamsipphonepolicy)
