---
title: 設定 Microsoft Teams Android 裝置使用者介面
ms.author: mitressl
author: flinchbot
manager: leopaiv
audience: ITPro
appliesto:
- Microsoft Teams
ms.reviewer: ''
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
description: 瞭解如何在 Teams Android 裝置上設定使用者介面。
ms.openlocfilehash: d3b625e4a54a6a9dcb75d0d1518a65b3e91c23185736672458b0fa1bbd6d55e1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54327349"
---
# <a name="set-microsoft-teams-android-devices-user-interface"></a>設定 Microsoft Teams Android 裝置使用者介面

Microsoft TeamsAndroid 裝置會根據指派給登入帳戶的授權類型，顯示特定的使用者介面。 您可以覆寫此行為，並控制顯示的介面。 本文將詳細說明如何選擇預設使用者介面，以及您可以如何使用 Powershell 原則變更介面。

在 Teams Android 裝置上有三種類型的使用者介面：

1. 使用者
2. 通用區域
3. 會議

如果您[指派使用者授權](/microsoftteams/user-access)給帳戶，例如 E3 或 E5 授權，則 Teams 裝置會顯示預設的使用者介面，該介面對於大多數使用者案例都是完整的功能。 不過，如果裝置執行的是特殊的功能，例如公用區域電話或會議室，則這些用法會有特定的使用者介面。

下列三個影像顯示使用者介面如何根據指派給使用者帳戶的授權進行變更。 在第一個影像中，會為使用者帳戶指派 E5 授權。 這是使用者授權，因此裝置會顯示預設的使用者介面：

:::image type="content" source="../media/TeamsAndroidDevices-UserMode1.jpg" alt-text="使用者模式介面":::

在此影像中，使用者帳戶已獲指派 [通用區域電話授權](/microsoftteams/set-up-common-area-phones)。 一般區域電話主要用於撥打和接聽電話。 如此一來，就會在顯示幕上顯示撥號盤墊：

:::image type="content" source="../media/TeamsAndroidDevices-CAP1.jpg" alt-text="公共區域電話介面":::

最後，此影像顯示已指派[Microsoft Teams 會議室標準授權](/MicrosoftTeams/rooms/rooms-licensing)的使用者帳戶。 Teams 會議室授權是用在會議室或共用空間中，因此使用者介面會變更，以方便您加入會議，方式是顯示行事曆的觀點：

:::image type="content" source="../media/TeamsAndroidDevices-Meeting.jpg" alt-text="會議介面":::

> [!NOTE]
> 變更使用者介面不會影響您使用其他授權功能的能力。 例如，即使「小組使用者授權」的預設視圖是「行事曆」視圖，但如果帳戶已正確授權和設定，仍然可以 (PSTN) 電話中撥打和接聽。

> [!IMPORTANT]
> 其他介面元素也會變更。 例如，若要防止使用者從公用區域電話或會議室裝置登出，請將這些裝置上的「登出」選項移至 [設定] 功能表中，該部分需要系統管理員許可權才能存取。

## <a name="override-automatic-user-interface-detection"></a>覆寫自動使用者介面偵測

在某些情況下，您可以選擇將授權指派給不符合其預定用途的帳戶。 例如，您可以將使用者授權指派給一個帳戶，以在 Android 上登入 Teams 會議室。 根據預設，您會看到使用者介面，而不是會議室介面。 若要覆寫預設介面，請建立新的[Teams IP 電話原則](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps)，並將其套用至該帳戶。

> [!NOTE]
> 指派給使用者帳戶的授權，必須至少要有與所需使用者介面相同的授權權利。 通用區域電話授權只會允許通用區域電話使用者介面。 會議室授權可讓會議室與公共區域電話使用者介面。 E3 或 E5 授權支援所有登入模式。

以下是如何覆寫自動授權偵測的範例。 在此範例中，假設名為 conf-adams@contoso.com 的會議室資源帳戶已獲指派 E3 授權。 當此帳戶已登入時，您想要讓使用者看到會議室使用者介面。

### <a name="create-a-new-policy-and-assign-to-user"></a>建立新的原則並指派給使用者

1. 啟動遠端 Windows PowerShell 會話，並使用下列 Cmdlet 連接至 Microsoft Teams：

    ``` Powershell
    Connect-MicrosoftTeams
    ```

2. 建立新的 Teams IP 電話原則，並將登入模式設定為 "MeetingSignIn"：

   ``` Powershell
   New-CsTeamsIPPhonePolicy –Identity 'Meeting Sign in' –Description 'Meeting Sign In Phone Policy' -SignInMode 'MeetingSignIn'

   ```

3. 您現在可以將此新原則指派給會議室資源帳戶：

   ``` Powershell
   Grant-CsTeamsIPPhonePolicy –Identity 'conf-adams@contoso.com' –PolicyName 'Meeting Sign In'
   ```

將原則授與會議室資源帳戶後，您將需要等候原則指派進行複製。 您也需要登出裝置，然後重新登入。
