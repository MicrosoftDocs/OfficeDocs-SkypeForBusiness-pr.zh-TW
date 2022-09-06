---
title: 設定 Microsoft Teams Android 裝置使用者介面
ms.author: dstrome
author: dstrome
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
- Teams_ITAdmin_Devices
description: 瞭解如何在 Teams Android 裝置上設定使用者介面。
ms.openlocfilehash: 830609d1bf02c38a2301c0d5a1b9e62ac836c908
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606832"
---
# <a name="set-microsoft-teams-android-devices-user-interface"></a>設定 Microsoft Teams Android 裝置使用者介面

Microsoft Teams Android 裝置可以根據指派給登入帳戶的授權類型來顯示特定的使用者介面。 您可以覆寫此行為並控制顯示的介面。 本文詳細說明如何選擇預設的使用者介面，以及如何使用 Powershell 原則變更介面。

Teams Android 裝置上有三種類型的使用者介面：

1. 使用者
2. 常用區域
3. 會議

如果您 [指派使用者授權](/microsoftteams/user-access) 給帳戶，例如 E3 或 E5 授權，Teams 裝置將會顯示預設的使用者介面，這是大部分使用者案例的完整功能。 不過，如果裝置正在執行特定功能，例如常見區域電話或會議室，這些使用方式會有特定的使用者介面。

下列三張影像顯示使用者介面如何根據指派給使用者帳戶的授權變更。 

## <a name="end-user-interface"></a>使用者介面 

使用者帳戶已指派 E5 授權。 這是使用者授權，因此裝置會顯示預設的使用者介面：

:::image type="content" source="../media/teams-android-devices-usermode1.jpg" alt-text="使用者模式介面。":::

## <a name="common-area-interface"></a>常見區域介面

在此影像中，使用者帳戶已獲指派 [通用區域電話授權](/microsoftteams/set-up-common-area-phones)。 常見區域電話主要用於撥打和接聽電話。 因此，撥號鍵台會顯示在顯示器上：

:::image type="content" source="../media/teams-android-devices-cap1.jpg" alt-text="常見的區域電話介面。":::

## <a name="meeting-interface"></a>會議介面

此影像顯示已指派[Microsoft Teams 會議室授權的](/MicrosoftTeams/rooms/rooms-licensing)使用者帳戶。 Teams 會議室授權的用途是用於會議室或共用空間，因此使用者介面會變更，以顯示行事曆檢視，讓您輕鬆加入會議：

:::image type="content" source="../media/teams-android-devices-meeting.jpg" alt-text="會議介面。":::

> [!NOTE]
> 變更使用者介面並不會影響您使用其他授權功能的能力。 例如，即使小組會議室授權的預設檢視是行事曆檢視，但如果帳戶已正確授權及設定，您仍可撥打和接收公用交換電話網 (PSTN) 電話。

> [!IMPORTANT]
> 介面的其他元素也會變更。 例如，若要防止使用者登出常見的區域電話或會議室裝置，這些裝置上的 [登出] 選項會移至需要系統管理員許可權才能存取之設定功能表的一部分。

## <a name="override-automatic-user-interface-detection"></a>覆寫自動使用者介面偵測

在某些情況下，您可能會選擇將授權指派給與其預定使用不相符的帳戶。 例如，您可以將使用者授權指派給在 Android 上用來登入Teams 會議室的帳戶。 根據預設，您會看到使用者介面，而不是會議室介面。 若要覆寫預設介面，請建立新的 [Teams IP Phone 原則](/powershell/module/skype/new-csteamsipphonepolicy) ，並套用至該帳戶。

> [!NOTE]
> 指派給使用者帳戶的授權必須至少與您想要的使用者介面擁有相同的授權權利。 通用區域電話授權只允許通用區域電話使用者介面。 會議室授權可讓會議室和常見區域電話使用者介面。 E3 或 E5 授權支援所有登入模式。

以下是如何覆寫自動授權偵測的範例。 在此範例中，假設名為 conf-adams@contoso.com 的會議室資源帳戶已獲指派 E3 授權。 當此帳戶已登入時，您希望使用者看到會議室使用者介面。

### <a name="create-a-new-policy-and-assign-to-user"></a>建立新原則並指派給使用者

1. 啟動遠端Windows PowerShell會話，並使用下列 Cmdlet 連線到 Microsoft Teams：

    ``` Powershell
    Connect-MicrosoftTeams
    ```

2. 建立新的 Teams IP Phone 原則，並將登入模式設定為 「MeetingSignIn」：

   ``` Powershell
   New-CsTeamsIPPhonePolicy –Identity 'Meeting Sign in' –Description 'Meeting Sign In Phone Policy' -SignInMode 'MeetingSignIn'

   ```

3. 您現在可以將這個新原則指派給會議室資源帳戶：

   ``` Powershell
   Grant-CsTeamsIPPhonePolicy –Identity 'conf-adams@contoso.com' –PolicyName 'Meeting Sign In'
   ```

將原則授與會議室資源帳戶之後，您必須等待原則指派複寫。 您也需要登出裝置並重新登入。

## <a name="impact-on-microsoft-teams-admin-center"></a>對 Microsoft Teams 系統管理中心的影響

Microsoft Teams 系統管理中心可讓您管理 Microsoft Teams 裝置。 如需使用 Teams 系統管理中心管理裝置的詳細資訊，請參閱 [在 Microsoft Teams 中管理您的裝置](device-management.md)。


Teams 系統管理中心提供管理 Teams 手機的功能。 手機會根據其功能篩選成三個索引標籤的其中之一：使用者電話、常見區域電話和會議電話。 

 :::image type="content" source="../media/teams-admin-center-phones-header.png" alt-text="Teams 系統管理中心的手機標頭。":::

與使用者介面偵測一樣，Teams 手機會根據指派給帳戶登入手機的授權進行分類。 例如，如果已指派通用區域電話授權的帳戶登入電話，則該電話會同時顯示在預設的 [ **所有電話** ] 區段以及 [ **通用區域電話** ] 區段中。

如果您希望手機顯示在不同的區段，您可以指派不同的授權給手機，或建立並指派 Teams IP Phone 原則，如 [上所述](#override-automatic-user-interface-detection)。
