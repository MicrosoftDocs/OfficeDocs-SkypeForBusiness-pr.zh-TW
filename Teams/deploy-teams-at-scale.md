---
title: 在 Microsoft Teams 中針對第一線工作人員大規模部署團隊
author: LanaChin
ms.author: v-lanachin
ms.reviewer: rahuldey
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何針對組織中的一線工作人員，以規模部署團隊。
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 561eaf310201b99ada9cce4dde49746d58d77088
ms.sourcegitcommit: 91cfb1a9c527d605300580c3acad63834ee54682
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/13/2022
ms.locfileid: "66046022"
---
# <a name="deploy-teams-at-scale-for-frontline-workers-in-microsoft-teams"></a>在 Microsoft Teams 中針對第一線工作人員大規模部署團隊

> [!NOTE]
> 這項功能目前處於私人預覽中。 如果您想要參與私人預覽，請在 [dscale@microsoft.com](mailto:dscale@microsoft.com)與我們連絡。

## <a name="overview"></a>概觀
 
您的組織可能有許多團隊可用來促進前線員工之間的通訊和共同作業，他們分散在不同的商店、地點和角色。 目前，部署、設定及管理這些團隊和使用者的解決方案並不簡單。

我們正在建置解決方案，讓系統管理員能夠以規模部署和管理團隊。

以下是目前可用來一次建立及管理大量團隊的功能概觀，以及近期的規劃。

||今天提供 |2022 年稍後版本  |
|---------|---------|---------|
|**每批可建立的團隊數目**|最多 100 個 |最多 500 個|
|**您可以為每個團隊新增的使用者數目**|最多 25 個|最多 25 個|

以縮放比例部署團隊可讓您：

- 使用預先建立的範本或您自己的自訂範本來建立團隊。
- 以擁有者或成員的身分將使用者新增至團隊。
- 從現有團隊新增或移除使用者，以規模管理團隊。
- 透過電子郵件持續收到通知，包括完成、狀態和錯誤 (如果有) 。 您可以選擇最多五個人通知您部署的每一批團隊狀態。 團隊擁有者和成員會在新增至團隊時自動收到通知。

## <a name="how-to-deploy-teams-at-scale"></a>如何大規模部署團隊

> [!NOTE]
> 在部署您的團隊之前，請先確認所有團隊擁有者都擁有Teams授權。

請依照下列步驟一次部署大量團隊。

### <a name="step-1-prepare-your-csv-files"></a>步驟 1：準備您的 CSV 檔案

您必須為您部署的每一批團隊建立兩個 CSV 檔案：

- **定義您正在建立之團隊的 CSV 檔案**。 此檔案必須包含這些必要的欄，順序如下：從第一欄開始：

    |欄名稱  |描述  |
    |---------|---------|
    |**團隊名稱**|團隊名稱。|
    |**現有的小組識別碼**|如果您要新增或移除現有團隊中的使用者，請指定團隊的團隊識別碼。|
    |**知名度**|團隊是否為公開 (貴組織中的任何人都可以加入) 或私人 (使用者需要團隊擁有者的核准才能加入) 。 選項為 **[公用** ] 和 [ **私人]**。|
    |**小組範本識別碼**|如果您要從預先建立或自訂範本建立團隊，請指定團隊範本識別碼。 如[需預先建立的團隊範本](get-started-with-teams-templates-in-the-admin-console.md)和識別碼清單，請參閱在 Teams 系統管理中心使用團隊範本開始。 如果您想要使用標準的預設團隊範本，請將此保留空白。|

- **對應您要新增至每個團隊之使用者的 CSV 檔案**。 此檔案必須包含這些必要的欄，順序如下：從第一欄開始：

    |欄名稱  |描述  |
    |---------|---------|
    |**使用者全名**|使用者的顯示名稱。|
    |**使用者 UPN 或 ID**|使用者主體名稱 (UPN) 或使用者識別碼。 例如，averyh@contoso.com。|
    |**團隊名稱**|團隊名稱。|
    |**ActionType**|無論您要新增或移除團隊中的使用者。 選項為 **AddMember** 和 **RemoveMember**。|
    |**擁有者或成員**|使用者是團隊擁有者或小組成員。 選項為 **[擁有者]** 和 **[成員]**。|

#### <a name="examples"></a>範例

請使用下列範例來協助您建立 CSV 檔案。 在這裡，我們已命名檔案、Teams.csv和Users.csv。

**Teams.csv**

|團隊名稱|現有的小組識別碼|知名度|小組範本識別碼|
|---------|---------|---------|---------|
|Contoso Microsoft Store 1||公共|com.microsoft.teams.template.retailStore|
|Contoso Microsoft Store 2||公共|com.microsoft.teams.template.retailStore|
|Contoso Microsoft Store 3||公共|com.microsoft.teams.template.retailStore|
|Contoso Microsoft Store 4||公共|com.microsoft.teams.template.retailStore|
|Contoso Microsoft Store 5||公共|com.microsoft.teams.template.ManageAProject|
|Contoso Microsoft Store 6||公共|com.microsoft.teams.template.ManageAProject|
|Contoso Microsoft Store 7||公共||
|Contoso Microsoft Store 8||私人|com.microsoft.teams.template.OnboardEmployees|
|Contoso Microsoft Store 9||私人|com.microsoft.teams.template.OnboardEmployees|
|Contoso Microsoft Store 10||私人|com.microsoft.teams.template.OnboardEmployees|

**Users.csv**

|使用者全名 |使用者 UPN 或 ID|團隊名稱|ActionType|擁有者或成員|
|---------|---------|---------|---------|---------|
|Avery Howard|averyh@contoso.com|Contoso Microsoft Store 1|AddMember|擁有者|
|Casey Jensen|caseyj@contoso.com|Contoso Microsoft Store 2|AddMember|擁有者|
|埃莉莉·Irwin|jessiei@contoso.com|Contoso Microsoft Store 3|AddMember|擁有者|
|曼吉耶特巴提亞文|manjeetb@contoso.com|Contoso Microsoft Store 4|AddMember|擁有者|
|Mikaela Lee|mikaelal@contoso.com|Contoso Microsoft Store 5|AddMember|擁有者|
|Morgan Conners|morganc@contoso.com|Contoso Microsoft Store 6|AddMember|成員|
|拉華|oscarw@contoso.com|Contoso Microsoft Store 7|AddMember|成員|
|RenePeletier|renep@contoso.com|Contoso Microsoft Store 8|AddMember|成員|
|雪梨馬多斯|sydneym@contoso.com|Contoso Microsoft Store 9|AddMember|成員|
|Violet Martinez|violetm@contoso.com|Contoso Microsoft Store 10|AddMember|成員|

### <a name="step-2-deploy-your-teams"></a>步驟 2：部署您的團隊

現在您已建立 CSV 檔案，可以設定環境並部署您的團隊。

您可以使用 ```New-CsBatchTeamsDeployment``` Cmdlet 提交一批要建立的團隊。 系統會針對每個批次產生協調識別碼。 接著， ```Get-CsBatchTeamsDeployment``` 您可以使用 Cmdlet 來追蹤每個批次的進度和狀態。

1. 安裝 PowerShell 版本 7 或更新版本。 如需逐步指引，請參閱[在 Windows 上安裝 PowerShell](/powershell/scripting/install/installing-powershell-on-windows)。
1. 以系統管理員模式執行 PowerShell。
1. 執行下列動作以卸載任何先前安裝Teams PowerShell 模組。

    ```powershell
    Uninstall-module -Name MicrosoftTeams -Force -Allversions
    ```

    如果您收到錯誤訊息，表示您已設定完成。 移至下一個步驟。
1. 下載並安裝[最新版的 Teams PowerShell 模組](https://www.powershellgallery.com/packages/MicrosoftTeams)。

1. 執行下列動作以連線至Teams。

    ```powershell
    Connect-MicrosoftTeams
    ```

    出現提示時，請使用您的系統管理員認證登入。

1. 執行下列動作以取得 Teams PowerShell 模組中的命令清單。

    ```powershell
    Get-Command -Module MicrosoftTeams
    ```

    確認並 ```New-CsBatchTeamsDeployment``` ```Get-CsBatchTeamsDeployment``` 列出。

1. 執行下列動作以部署一批團隊。 在此命令中，您指定 CSV 檔案的路徑，以及最多五個收件者的電子郵件地址，以通知有關此部署的資訊。

    ```powershell
    New-CsBatchTeamsDeployment -TeamsFilePath "Your CSV file path" -UsersFilePath "Your CSV file path" -UsersToNotify "Email addresses" 
    ```

    例如：

    ```powershell
    New-CsBatchTeamsDeployment -TeamsFilePath "C:\dscale\Teams.csv" -UsersFilePath "C:\dscale\Users.csv" -UsersToNotify "adminteams@contoso.com,adelev@contoso.com"
    ```

    收件者會收到有關部署狀態的電子郵件通知。 電子郵件包含您提交的批次協調識別碼，以及可能發生的任何錯誤。

1. 執行下列動作以檢查您提交的批次狀態。

    ```powershell
    Get-CsBatchTeamsDeploymentStatus -OrchestrationId "OrchestrationId"
    ```

## <a name="send-us-feedback"></a>傳送意見反應給我們

我們很重視您的意見反應。 我們歡迎我們提供可用性、可靠性和效 &mdash; 能！

電子郵件 [dscale@microsoft.com](mailto:dscale@microsoft.com) ，如果有的話，請包含您的編排識別碼和錯誤檔案。

## <a name="related-articles"></a>相關文章

- [Teams PowerShell 概觀](teams-powershell-overview.md)
