---
title: 設定Microsoft Teams Android 裝置使用者介面
ms.author: mitressl
author: flinchbot
manager: serdars
audience: ITPro
appliesto:
- Microsoft Teams
ms.reviewer: ''
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
description: 瞭解如何在 Android 裝置上Teams介面。
ms.openlocfilehash: cf0c60fa5073ee2a3915f2450900865bc058e295
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2022
ms.locfileid: "61767426"
---
# <a name="set-microsoft-teams-android-devices-user-interface"></a>設定Microsoft Teams Android 裝置使用者介面

Microsoft Teams Android 裝置可以根據指派給已登錄帳戶之授權類型來顯示特定的使用者介面。 您可以重寫此行為，並控制顯示哪個介面。 本文詳細說明預設使用者介面的選用方式，以及如何使用 Powershell 策略變更介面。

Android 裝置上的使用者介面Teams類型：

1. 使用者
2. 共同區域
3. 會議

如果您[將使用者](/microsoftteams/user-access)授權指派給帳戶 ，例如 E3 或 E5 授權，Teams 裝置會顯示預設使用者介面，此介面在大部分使用者案例中都提供完整功能。 不過，如果裝置正在執行特定功能 ，例如公用區域電話或會議室，則這些使用方式會提供特定的使用者介面。

下列三個影像顯示使用者介面如何根據指派給使用者帳戶授權而變更。 第一個影像會為使用者帳戶指派 E5 授權。 這是使用者授權，因此裝置會顯示預設的使用者介面：

:::image type="content" source="../media/teams-android-devices-usermode1.jpg" alt-text="使用者模式介面。":::

在此影像中，使用者帳戶已指派一般 [地區電話授權](/microsoftteams/set-up-common-area-phones)。 一般地區電話主要用來撥打和接聽電話。 因此，撥號鍵台會顯示在顯示器上：

:::image type="content" source="../media/teams-android-devices-cap1.jpg" alt-text="公用區域電話介面。":::

最後，此影像顯示已指派授權[Microsoft Teams 會議室標準版使用者帳戶。](/MicrosoftTeams/rooms/rooms-licensing) Teams 會議室授權應用於會議室或共用空間，因此使用者介面會變更，以便顯示日曆視圖，輕鬆加入會議：

:::image type="content" source="../media/teams-android-devices-meeting.jpg" alt-text="會議介面。":::

> [!NOTE]
> 變更使用者介面不會影響您使用其他授權功能的能力。 例如，即使小組會議室授權的預設視圖是 [日曆視圖，如果帳戶已正確授權及配置，您仍然可以撥打和接聽公用交換電話網路 (PSTN) 電話。

> [!IMPORTANT]
> 介面的其他元素會變更。 例如，若要防止使用者登出公用區域電話或會議室裝置，這些裝置上的「登出」選項會移至需要系統管理員許可權才能存取的設定功能表的一部分。

## <a name="override-automatic-user-interface-detection"></a>重寫自動使用者介面偵測

在某些情況下，您可以選擇將授權指派給與預定用途不相符的帳戶。 例如，您可以指派使用者授權給帳戶，以在 Android 上Teams 會議室帳戶。 根據預設，您會看到使用者介面，而不是會議室介面。 若要重寫預設介面，請建立一個新的 IP Teams[原則電話並](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps)適用于該帳戶。

> [!NOTE]
> 指派給使用者帳戶的授權必須至少擁有與所需使用者介面相同的授權權利。 公用區域電話僅允許公用區域電話使用者介面。 會議室授權允許會議室和公用區域電話使用者介面。 E3 或 E5 授權支援所有登錄模式。

以下是如何取代自動授權偵測的範例。 在此範例中，假設名為 conf-adams@contoso.com 的會議室資源帳戶已指派 E3 授權。 當此帳戶已登錄時，您希望使用者看到會議室使用者介面。

### <a name="create-a-new-policy-and-assign-to-user"></a>建立新策略並指派給使用者

1. 啟動遠端Windows PowerShell會話，然後使用Microsoft Teams Cmdlet 來連接到遠端會話：

    ``` Powershell
    Connect-MicrosoftTeams
    ```

2. 建立新的 IP Teams ip 電話，並設定 「MeetingSignIn」的登錄模式：

   ``` Powershell
   New-CsTeamsIPPhonePolicy –Identity 'Meeting Sign in' –Description 'Meeting Sign In Phone Policy' -SignInMode 'MeetingSignIn'

   ```

3. 現在您可以將這個新政策指派給會議室資源帳戶：

   ``` Powershell
   Grant-CsTeamsIPPhonePolicy –Identity 'conf-adams@contoso.com' –PolicyName 'Meeting Sign In'
   ```

將策略授予會議室資源帳戶之後，您必須等待複製該策略指派。 您也需要登出裝置並再次重新登錄。

## <a name="impact-on-microsoft-teams-admin-center"></a>對系統管理Microsoft Teams的影響

Microsoft Teams系統管理中心可讓您管理Microsoft Teams裝置。 有關使用系統管理中心管理Teams，請參閱在 Microsoft Teams[中管理您的Microsoft Teams。](device-management.md)


Teams系統管理中心提供管理Teams功能。 電話會依據其功能篩選為三個選項卡中的一個：使用者電話、一般區域電話和會議電話。 

 :::image type="content" source="../media/teams-admin-center-phones-header.png" alt-text="系統管理中心Teams電話標題。":::

與使用者介面偵測一樣，Teams手機會根據指派給帳戶的登錄授權來分類。 例如，如果指派一般地區電話授權的帳戶已登錄至電話，則該電話會顯示在預設的所有電話區段，以及公用區域電話區段。 

如果您希望電話出現在不同的區段，您可以指派不同的授權給電話，或建立並指派 Teams IP 電話策略。[如上所述。](#override-automatic-user-interface-detection)
