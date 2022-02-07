---
title: 設定 Android 裝置Teams自動答案
author: KarliStites
ms.author: kastites
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
ms.custom: null
description: 瞭解如何使用 PowerShell 在 Android Microsoft Teams 會議室和視Teams裝置上設定自動接聽功能。
---

# <a name="set-up-auto-answer-for-microsoft-teams-rooms-on-android-and-teams-video-phone-devices"></a>在 Android 和視Microsoft Teams 會議室裝置上Teams自動接聽

本文將協助您設定 Android Microsoft Teams 會議室 和視Teams裝置上的自動Teams功能。 自動接聽可讓您組織中具有系統管理許可權的人變更其裝置設定，以自動接受傳入的會議邀請，並自動接受視音訊通話。

## <a name="enable-auto-answer-with-powershell"></a>使用 PowerShell 啟用自動答案

使用下列屬性在 Android 和視訊Microsoft Teams 會議室裝置上Teams自動接聽：

- **Set-CsTeamsCallingPolicy -AutoAnswerEnabledType**
- **Set-CsTeamsIPPhonePolicy -SignInMode**

### <a name="1-turn-on-auto-answer-for-incoming-meeting-invites"></a>1. 開啟傳入會議邀請的自動答案

您可以使用 **Set-CsTeamsCallingPolicy -AutoAnswerEnabledType** 開啟傳入會議邀請的自動答案。 自動答案 **預設為** 關閉。 此原則僅適用于傳入的會議邀請，且不支援其他通話類型。 請參閱 [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy) 以在 Cmdlet 上獲得詳細資訊。

```powershell
Set-CsTeamsCallingPolicy -AutoAnswerEnabledType Enabled
```

### <a name="2-set-the-device-sign-in-mode"></a>2. 設定裝置登錄模式

您可以使用 **Set-CsTeamsIPPhonePolicy -SignInMode** 設定裝置登入模式，以判斷登入 Teams。 請參閱 [Set-CsTeamsIPPhonePolicy](/powershell/module/skype/set-csteamsipphonepolicy) 以在 Cmdlet 上查看詳細資訊。

有三種用於登錄模式的選項：

- **UserSignIn：** 啟用個別使用者Teams通話體驗。
- **CommonAreaPhoneSignIn：** 在手機上啟用常見的地區電話體驗。
- **MeetingSignIn：** 在手機上啟用會議室體驗。

例如，下列策略將登錄模式設定為會議室體驗。

```powershell
Set-CsTeamsIPPhonePolicy -Identity Device -SignInMode MeetingSignIn
```

### <a name="configure-device-settings"></a>設定裝置設定

啟用自動回應後，具有系統管理許可權的使用者可以在其裝置設定中開啟此功能。 若要在裝置層級啟用此功能，您必須開啟自動 **接受傳入的會議邀請**。 您也可以開啟影片 **自動接受** 功能。 這兩個設定預設為關閉。

## <a name="related-topics"></a>相關主題

[Microsoft 支援：通話與裝置](https://support.microsoft.com/office/calls-and-devices-4d96653e-6176-4978-98ab-2c19df137e43#ID0EBBD=Devices)

[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

[Set-CsTeamsIPPhonePolicy](/powershell/module/skype/set-csteamsipphonepolicy)
