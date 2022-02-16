---
title: 設定共同區域電話授權
ms.author: czawideh
author: cazawideh
manager: serdars
ms.date: 1/28/2022
ms.reviewer: kponnus
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: '瞭解如何設定大廳、接待區和會議室的公用區域電話 '
ms.openlocfilehash: 144e32e1bf56bc3e2d64d0c6a1a137fd501442b7
ms.sourcegitcommit: 5aae5eace62e491dac655882d24974824ce1aa07
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/16/2022
ms.locfileid: "62856661"
---
# <a name="deploy-common-area-phones-for-microsoft-teams"></a>部署常用的地區電話Microsoft Teams

一般地區電話會放在大廳等區域，或是許多人可以撥打的另一個區域;例如，接待區、大廳或會議電話。 一般地區電話會使用與共同區域授權相關的帳戶電話登錄。

本文提供如何部署和設定手機Teams共用空間的公用區域電話概觀。 為獲得更完整的會議室體驗 ，包括音訊會議，請考慮使用會議室裝置會議室專用會議室授權。

## <a name="overview"></a>概觀

公用區域電話授權支援： 


| &nbsp;  |  公用區域電話  |
|---------|---------|
|商務用 Skype |   &#x2714; |
|Microsoft Teams |   &#x2714; |
|電話系統 |    &#x2714; |
|音訊會議 |       &#x2718; &sup1;  |
|Microsoft Intune |    &#x2718; |
|全球可用性 |       &#x2718; &sup2;  |
|通道可用性 |    EA、EAS、CSP、GCC、EES、Web Direct  |
|      |         |

&sup1;一般地區電話可以透過會議召集人提供的撥入號碼加入音訊會議

&sup2;在主權雲端中不可用  

>[!NOTE]
> 在 商務用 Skype Server 中建立的共同區域電話物件帳戶無法移Microsoft Teams。 請遵循本文中的步驟，重新建立這些帳戶Teams並如有必要，請遷移您的 PTSN 連接。

## <a name="step-1---buy-the-licenses"></a>步驟 1 - 購買授權

首先，您需要購買一般區域電話 (CAP) 授權，並確認您擁有經過認證的電話。 若要搜尋並深入瞭解認證電話，請前往[Microsoft Teams裝置](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)。

1. 在 Microsoft 365 系統管理中心，請前往 **BillingPurchase** ****  >  服務。 

2. If the **View by category** section isn't already displayed, go to **Purchase from Microsoft**, and select **View products**. 然後選取 **共同合作與通訊**。  

3. 在產品清單中，尋找 **常用區域電話** 並選取詳細 **資料**。

4. 輸入所需的授權數量，然後 **選取購買。**

>[!NOTE]
>如果您在環境中使用 Intune，而且有要求裝置合規性的條件式存取規則，您必須將 Azure Active Directory Premium 方案 1 和 Intune 授權指派給公用地區電話的裝置帳戶。
>
>常見的區域電話可能會受到條件式存取規則和其他身分識別組組的影響，例如多重要素驗證。 請參閱[Android 裝置Teams驗證](devices/authentication-best-practices-for-android-devices.md)最佳做法以深入瞭解。

## <a name="step-2---create-a-new-user-account-and-assign-licenses"></a>步驟 2 - 建立新使用者帳戶並指派授權

### <a name="using-the-microsoft-365-admin-center"></a>使用 Microsoft 365 系統管理中心

如果您要一次部署多個公用區域電話，請瞭解如何使用 PowerShell 建立帳戶和 [指派授權](#using-powershell)。

如果您要部署一個裝置：

1. 在 Microsoft 365 系統管理中心，請前往 **UserActive**  >  **Usersadd** ****  >  使用者。

2. 輸入名字的使用者名稱，例如「主」，第二個名稱輸入「接收」。

3. 如果顯示名稱無法像「主要接收」一樣自動生成，請輸入顯示名稱。

4. 輸入使用者名稱，例如「MainReception」或「Mainlobby」。

5. 手動設定常用地區電話的密碼，以防止。 若要這麼做，請取消勾選 **自動建立密碼，** 並要求該使用者在首次登錄 **時變更密碼**。  

    >[!Important]
    > 強烈建議您手動設定一般地區電話的密碼，以防止使用者發生登錄問題。

6. 選取裝置的使用位置，並將公用區域電話授權指派給帳戶。 如果需要任何其他授權 ，例如通話方案，請指派授權。

>[!NOTE]
> 您不需要新增授權電話系統授權。 它包含在共同區域授權電話中。
>
>如果您不是使用系統直接Microsoft 電話或運算子連線，您可能會想要新增通話方案授權。 有關授權詳細資訊，請參閱Microsoft Teams[附加元件授權](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

### <a name="using-powershell"></a>使用 PowerShell

當您想要一次建立及指派多個使用者帳戶授權時，請使用 PowerShell。 請參閱[使用 powerShell Microsoft 365](/microsoft-365/enterprise/create-user-accounts-with-microsoft-365-powershell?view=o365-worldwide)建立使用者帳戶，[以及使用 PowerShell](/microsoft-365/enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell?view=o365-worldwide) Microsoft 365指派授權給使用者帳戶以瞭解更多資訊。

## <a name="step-3---set-policies-for-common-area-phones"></a>步驟 3 - 設定一般地區電話的政策

使用策略來控制哪些功能可供使用者在一般地區電話上使用。

>[!NOTE]
>指派策略之後，請登出電話並再次重新登錄。 最多可能需要一小時的時間，策略指派才生效。

### <a name="ip-phone-policies"></a>IP 電話政策

使用帳戶已指派共同區域或授權電話的手機會顯示共同區域使用者體驗。

如果您想要重寫電話的預設介面，請考慮建立 [IP 電話策略](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps)。 例如，如果公用區域中使用公用區域電話，請設定 IP 電話政策，以限制搜尋貴組織的全域通訊錄並封鎖電話機。 請參閱[設定Teams Android 裝置使用者介面以](devices/Teams-Android-devices-user-interface.md)深入瞭解。

### <a name="calling-policies"></a>通話原則

使用通話策略啟用私人通話、使用呼叫轉轉，或同時撥打一般地區電話。 如需[深入瞭解，](teams-calling-policy.md)請參閱在 Teams 通話和呼叫轉Teams轉。

根據預設，一般地區電話不會啟用通話停駐。 您需要建立一個策略來啟用它。 如需[深入瞭解，](call-park-and-retrieve.md)請參閱在 Microsoft Teams中呼叫駐Microsoft Teams並取回。

## <a name="step-4---acquire-and-assign-phone-numbers"></a>步驟 4 - 取得及指派電話號碼

請參閱 [管理貴組織的電話號碼](manage-phone-numbers-landing-page.md) ，瞭解如何根據您的 PSTN 連接選項取得和指派電話號碼。

## <a name="step-5---sign-in"></a>步驟 5 - 登錄

建立及設定使用者帳戶後，您可以登錄手機。 根據您部署的手機個個，您擁有三個登錄選項：

- [本地登錄](#local-sign-in)
- [從另一個裝置登錄](#sign-in-from-another-device)
- [使用系統管理中心Teams登錄](#sign-in-using-the-teams-admin-center)

### <a name="local-sign-in"></a>本地登錄

若要使用使用者名稱和密碼在本地登錄： 

1. 開啟公用區域電話

2. 選取 **在此裝置上登錄**

3. 請遵循裝置上的登錄指示。 一旦登錄，電話會顯示常見的地區電話使用者體驗。

### <a name="sign-in-from-another-device"></a>從另一個裝置登錄

您也可以使用程式碼，從另一部裝置上登錄一般地區電話。 當您以這種方式進行登錄時，您將在另一個裝置上輸入使用者名稱和密碼，而不是在電話本身。

1. 首先，在常見的地區電話上，尋找在登錄畫面上顯示的代碼。

2. 在另一個裝置上，前往 https://www.microsoft.com/devicelogin 。

3. 輸入程式碼，然後按照指示完成登錄。

### <a name="sign-in-using-the-teams-admin-center"></a>使用系統管理中心Teams登錄

做為系統管理員，您可以從系統管理中心遠端Teams電話。 這是一次部署大量電話時最有效率的登錄方法。 如需深入瞭解，請參閱遠端Teams[並登錄 Android](devices/remote-provision-remote-login.md)裝置。

## <a name="next-steps"></a>後續步驟

現在，您為貴組織設定並登錄了共同的區域電話，您可以在系統管理中心Teams電話。 請參閱[Microsoft Teams：管理您的裝置](devices/device-management.md)以深入瞭解。

## <a name="related-topics"></a>相關主題

- [遠端Microsoft Teams更新裝置](devices/remote-update.md)
- [管理Microsoft Teams標記](devices/manage-device-tags.md)
- [Microsoft Teams裝置健康情況監控](alerts/device-health-status.md)
