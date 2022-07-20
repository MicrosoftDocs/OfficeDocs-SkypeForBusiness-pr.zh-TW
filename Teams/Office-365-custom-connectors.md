---
title: 管理 Microsoft 365 和自訂連接器
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: lucarras
search.appverid: MET150
f1.keywords:
- NOCSH
description: 瞭解連接器如何經常將內容和更新直接傳送至 Teams 頻道，讓您的團隊持續更新，以供您使用的服務使用。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: fb056cbee4dc1d56a6cd967d3f46c3f0680e9b73
ms.sourcegitcommit: 89904ab4116294ad9e4fd407feba8d7e3eefef10
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/19/2022
ms.locfileid: "66880227"
---
# <a name="manage-microsoft-365-and-custom-connectors"></a>管理 Microsoft 365 和自訂連接器

為了持續更新您的團隊，連接器會將常用的內容和服務更新直接傳送到 Teams 頻道。 透過連接器，您的 Teams 使用者可以從 Trello、Wunderlist、GitHub 和 Azure DevOps Services 等熱門服務接收更新。 更新會直接張貼到小組中的聊天串流中。

Microsoft 365 連接器同時搭配 Microsoft Teams 和 Microsoft 365 群組使用，可讓所有成員更輕鬆地保持同步，並快速接收相關資訊。 Microsoft Teams 和 Exchange 都使用相同的連接器模型，可讓您在兩個平臺內使用相同的連接器。 不過，如果您停用為 Microsoft 365 群組設定的任何連接器，它也會停用 Microsoft 365 群組建立連接器的功能。

如果團隊許可權允許，團隊中的任何成員都可以使用連接器將小組連線到熱門的雲端服務，而且所有小組成員都會收到來自該服務的活動通知。 最初設定連接器的成員離開之後，連接器仍會繼續運作。 任何具有新增或移除許可權的小組成員都可以修改其他成員設定的連接器。

## <a name="enable-or-disable-connectors-in-teams"></a>在 Teams 中啟用或停用連接器

Exchange Online PowerShell V2 模組使用新式驗證，並可與稱為 MFA 的多重要素驗證搭配使用，以連線至 Microsoft 365 中所有 Exchange 相關 PowerShell 環境。 系統管理員可以使用 Exchange Online PowerShell 來停用整個租使用者或特定群組信箱的連接器，這會影響該租使用者或信箱中的所有使用者。 無法針對少數特定使用者停用。 此外，政府社群雲端預設會停用連接器，稱為 GCC 租使用者。

租使用者設定會覆寫群組設定。 例如，如果系統管理員為群組啟用連接器，並在租使用者上停用連接器，群組的連接器就會停用。 若要在 Teams 中啟用連接器，請使用包含或不含 MFA 的新式驗證來[連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps#connect-to-exchange-online-powershell-using-modern-authentication-with-or-without-mfa&preserve-view=true)。

若要啟用或停用連接器，請在 Exchange Online PowerShell 中執行下列命令：

* 若要停用租使用者的連接器： `Set-OrganizationConfig -ConnectorsEnabled:$false` 。
* 若要停用租使用者可採取動作的訊息： `Set-OrganizationConfig -ConnectorsActionableMessagesEnabled:$false` 。
* 若要啟用 Teams 的連接器，請執行下列命令：
  * `Set-OrganizationConfig -ConnectorsEnabled:$true`
  * `Set-OrganizationConfig -ConnectorsEnabledForTeams:$true`
  * `Set-OrganizationConfig -ConnectorsActionableMessagesEnabled:$true`

如需 PowerShell 模組交換的詳細資訊，請參閱 [Set-OrganizationConfig](/powershell/module/exchange/Set-OrganizationConfig?view=exchange-ps&preserve-view=true)。 若要啟用或停用 Outlook 連接器，請 [在 Microsoft Outlook 中將應用程式連線到您的群組](https://support.microsoft.com/topic/connect-apps-to-your-groups-in-outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab)。

<!--- TBD: Find out how can we get to know about completion of customer migration.
Delete this section after customer migration to new Webhook URL is complete.
--->

## <a name="publish-connectors-for-your-organization"></a>發佈貴組織的連接器

如果您希望自訂連接器僅供組織中的使用者使用，您可以將自訂連接器應用程式上傳至組織的應用程式目錄。 上傳應用程式套件之後，使用者可以從組織的應用程式目錄安裝連接器，並可在小組中設定和使用連接器。

<!---TBD: Check if these instructions are for admins or end-users. I cannot find these options either in Teams or in TAC.

To set up a connector:

1. Select **Apps** from the left navigation bar.
1. In the **Apps** section, select **Connectors**.
1. Select the connector that you want to add.
1. From the pop-up menu, select **Add to a team**.
1. In the search box, type a team or channel name.
1. Select **Set up a Connector** from the pop-up menu in the bottom right corner of the dialog window.
--->

> [!IMPORTANT]
> 自訂連接器不適用於政府社群雲端 (GCC) 、政府社群Cloud-High (GCCH) ，以及美國商務部 (DOD) 。

若要在團隊或頻道中使用連接器，請從頻道右上角開啟 [其他選項] 功能表。 從功能表中選取 **[連接器** ]，然後找出或搜尋所需的連接器。 視需要設定選取的連接器。

:::image type="content" source="media/connectors-selection-ui.png" alt-text="從頻道右上角的 [更多選項] 將連接器新增至 Teams 中的頻道。":::

## <a name="update-url-of-a-connector"></a>更新連接器的 URL

Teams 連接器正轉換到新的 URL 以加強安全性。 在轉換期間，您會收到更新已設定之連接器的通知。 請儘早更新您的連接器，以防止任何對連接器服務的干擾。 若要更新連接器：

1. 在 [連接器設定] 頁面上，核取設定的連接器旁的 [ **注意必要** ] 訊息。

   :::image type="content" source="media/Teams_Attention_Required_message.png" alt-text="[注意必要] 訊息的螢幕擷取畫面。":::

1. 若要重新建立內送 webhook 連接器的連線，請選取 **[更新 URL** ]，然後使用產生的 webhook URL。

   :::image type="content" source="media/Teams_update_URL_button.png" alt-text="[更新 URL] 按鈕的螢幕擷取畫面。":::

1. 對於其他連接器類型，請移除連接器並重新建立連接器設定。 系統會顯示最新訊息的 **URL** 。

   :::image type="content" source="media/Teams_URL_up_to_date.png" alt-text="URL 是最新郵件的螢幕擷取畫面。":::

## <a name="related-articles"></a>相關文章

* [自訂連接器和網路任務概觀](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)
* [建立Office 365連接器](/microsoftteams/platform/webhooks-and-connectors/how-to/connectors-creating)
