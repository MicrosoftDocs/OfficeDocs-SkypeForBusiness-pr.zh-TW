---
title: 在 Microsoft 團隊中通話駐留與取回
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 04/12/2019
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.callparkpolicies.overview
- seo-marvel-apr2020
description: 瞭解如何使用通話駐留及取回功能，在雲端的小組服務中保持通話。
ms.openlocfilehash: 8c6f275ea1b1aac9bfa011fba76d17aeb1811e10
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582650"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>在 Microsoft 團隊中通話駐留與取回

通話駐留與取回功能可讓使用者在雲端的小組服務中保留通話。 當通話停用時，服務會產生唯一的呼叫檢索程式碼。 停用通話的使用者，或其他人可以使用該程式碼和支援的 app 或裝置來檢索通話。 

使用通話駐留的一些常見案例如下： 

- [接待員] 負責在工廠中使用某個人的通話。 然後，接待員會宣佈通話，並將代碼編號放在公用位址系統上。 通話的使用者可以在工廠中挑選 [團隊電話]，然後輸入程式碼來檢索通話。
- 使用者在行動裝置上公園通話，因為裝置電池已用完電源。 然後，使用者可以輸入程式碼來從小組的手機中檢索通話。
- 支援代表會公園客戶通話，並在小組頻道上傳送公告，讓專家來取得通話並協助客戶。 專家在 [團隊用戶端] 中輸入程式碼來檢索通話

> [!IMPORTANT]
> 此功能僅適用于 [僅限團隊部署模式]。 如需有關團隊部署模式的詳細資訊，請參閱[瞭解 Microsoft 團隊及商務用 Skype 共存與互通性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>需要授權

若要寄存與取回通話，使用者必須是企業語音使用者，且系統管理員必須為使用者授予通話駐留原則。 如需授權模型的詳細資訊，請參閱[Microsoft 團隊服務說明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)。

## <a name="call-park-and-retrieve-feature-availability"></a>通話駐留及取得功能可用性

下列用戶端和裝置目前支援通話駐留和取回。 在只有 PSTN 連線的情況下，在 [僅限團隊] 模式中支援 (。 ) 

| 功能 | 團隊桌面 | 團隊 Mac 應用程式 | 團隊 Web App (邊緣)  |團隊行動 iOS/Android 應用程式 | 團隊 IP 電話 | 商務用 Skype IP 電話 |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| 寄存通話 | 是 | 是 | 是 | 是 | 是 | 否 |
| 檢索寄存通話 | 是 | 是 | 是 | 是 | 是 | 否 |
| Unretrieved 電話鈴聲傳回 | 是 | 是 | 是 | 是 | 是 | 否 |

## <a name="configure-call-park-and-retrieve"></a>設定通話寄存與取回

您必須是系統管理員，才能設定通話駐留和取回，而且預設是停用此功能。 您可以為使用者啟用它，並使用通話駐留原則來建立使用者群組。 當您將相同的原則套用到一組使用者時，他們可以在自己的情況下寄存和取回通話。 若要設定使用者的通話駐留，並建立通話駐留使用者群組，請遵循下列的[指派通話駐留原則](#assign-a-call-park-policy)程式。

如需如何使用通話公園和取得功能的相關資訊，請參閱[在團隊中寄存通話](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)。

### <a name="enable-a-call-park-policy"></a>啟用通話駐留原則

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [**語音**  >  **通話寄存原則**]。
2. 選取 [**新增**]。
3. 為原則命名，然後將 [**允許通話駐留**] 切換為 [**開啟**]。
4. 選取 [**儲存**]。

#### <a name="using-powershell"></a>使用 PowerShell

請參閱[新-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)。

### <a name="edit-a-call-park-policy"></a>編輯通話寄存原則

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [**語音**  >  **通話寄存原則**]。
2. 按一下原則名稱左邊的，然後按一下 [**編輯**]，選取原則。
3. [**允許通話駐留**] 切換為 [**關閉**] 或 [**開啟**]。
4. 按一下 [儲存]****。

#### <a name="using-powershell"></a>使用 PowerShell

請參閱[設定 CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)。 例如，若要變更預設設定，請執行下列動作：

  ```PowerShell
  Set-CsTeamsCallParkPolicy -Identity Global -AllowCallPark $true
  ```

### <a name="assign-a-call-park-policy"></a>指派通話駐留原則

[!INCLUDE [assign-policy](includes/assign-policy.md)]
 
另請參閱[授與 CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)。

## <a name="troubleshooting"></a>疑難排解

如果使用者看不到 [寄存] 或 [取得] 按鈕： 

- 檢查使用者是否已啟用通話駐留原則。 

如果使用者嘗試檢索通話，但卻失敗，請檢查下列專案：

- 確認使用者使用的是 [團隊用戶端] 或 [小組啟用的裝置/電話]
- [群組]-使用者是 [呼叫駐留] 群組的成員，而這是以擁有相同的小組通話駐留原則指派的方式為基礎。 
- 孤島模式–在團隊安全島模式中無法使用通話駐留與取回功能。
- 通話已被檢索或終止。

## <a name="related-topics"></a>相關主題

[在團隊中寄存通話](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[指派策略給小組中的使用者](assign-policies.md)
