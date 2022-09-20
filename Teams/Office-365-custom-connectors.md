---
title: 管理 Microsoft 365 和自訂連接器
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: lucarras
search.appverid: MET150
f1.keywords:
- NOCSH
description: 了解連接器如何透過您經常使用的服務，將內容和更新直接傳遞至 Teams 頻道中，進而使您的團隊保持最新狀態。
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5e61a6705f470ee93c7169effdd56f35ca0dd6f4
ms.sourcegitcommit: ceba5fd8f098c8d0eafaffe5c5301c845a3ae7ab
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2022
ms.locfileid: "67837353"
---
# <a name="manage-microsoft-365-and-custom-connectors"></a>管理 Microsoft 365 和自訂連接器

若要讓您的小組保持更新，連接器會直接將常用的內容和服務更新傳遞至 Teams 頻道。 有了連接器，您的 Teams 使用者就能接收來自 Trello、Wunderlist、GitHub 和 Azure DevOps 服務等熱門服務的更新。 更新會直接張貼到小組中的聊天串流中。

Microsoft 365 連接器同時用於 Microsoft Teams 和 Microsoft 365 群組。 它讓所有成員都更容易保持同步，並快速接收相關資訊。 您可以同時在 Microsoft Teams 和 Microsoft Exchange 中使用相同的連接器。 不過，如果您停用為 Microsoft 365 群組所設定的任何連接器，其也會停用 Microsoft 365 群組建立連接器的能力。

如果小組權限允許，小組的任何成員都可以將其小組連線至熱門的雲端服務，而且所有的小組成員都會收到該服務的活動通知。 在最初設定連接器的成員離開之後，連接器會繼續工作。 任何具有新增或移除權限的小組成員都可以修改其他成員的連接器設定。

## <a name="enable-or-disable-connectors-in-teams"></a>在 Teams 中啟用或停用連接器

Exchange Online PowerShell V2 模組使用新式驗證，並使用多重要素驗證 (MFA) 來連線到 Microsoft 365 中所有與 Exchange 相關的 PowerShell 環境。 系統管理員可以使用 Exchange Online PowerShell 來停用整個租用戶或特定群組信箱的連接器，這會影響該租用戶或信箱中的所有使用者。 無法為少數特定使用者停用。 此外，根據預設，政府社群雲端 (GCC) 環境會停用連接器。

> [!NOTE]
> 在政府雲端社群 (GCC) 環境中，連接器會根據預設定為停用。 若要啟用這些參數，請使用 `SetOrganizationConfig` Cmdlet 將 `ConnectorsEnabled` 或 `ConnectorsEnabledForTeams` 參數設定為 `$true`。 連線到 [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps&preserve-view=true)。

租用戶設定會覆寫群組設定。 例如，如果系統管理員啟用群組的連接器，並停用租用戶上的連接器，則群組的連接器會停用。 若要在 Teams 中啟用連接器，請使用新式驗證 (無論是否使用 MFA) [以連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps#connect-to-exchange-online-powershell-using-modern-authentication-with-or-without-mfa&preserve-view=true)。

若要啟用或停用連接器，請在 Exchange Online PowerShell 中執行下列命令：

* 若要停用租用戶的連接器：`Set-OrganizationConfig -ConnectorsEnabled:$false`。
* 若要停用租用戶的可採取動作之訊息：`Set-OrganizationConfig -ConnectorsActionableMessagesEnabled:$false`。
* 若要啟用 Teams 的連接器，請執行下列命令：
  * `Set-OrganizationConfig -ConnectorsEnabled:$true`
  * `Set-OrganizationConfig -ConnectorsEnabledForTeams:$true`
  * `Set-OrganizationConfig -ConnectorsActionableMessagesEnabled:$true`

有關 PowerShell 模組交換的詳細資訊，請參閱 [Set-OrganizationConfig](/powershell/module/exchange/Set-OrganizationConfig?view=exchange-ps&preserve-view=true)。 若要啟用或停用 Outlook 連接器，[請將應用程式連接到 Microsoft Outlook 中的群組](https://support.microsoft.com/topic/connect-apps-to-your-groups-in-outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab)。

## <a name="publish-connectors-for-your-organization"></a>發佈貴組織的連接器

若要讓自訂連接器可供貴組織的使用者使用，請上傳自訂連接器應用程式至貴組織的應用程式目錄。 組織中的使用者可以在小組中安裝、設定及使用連接器。

> [!IMPORTANT]
> 自訂連接器不適用於政府社群雲端 (GCC)、政府社群雲端-高 (GCCH) 和美國國防部 (DOD) 環境。

若要在小組或頻道中使用連接器，請從頻道右上角開啟 [其他選項] 功能表。 從功能表中選取 **[連接器]** 然後尋找或搜尋所需的連接器。 如有必要，請設定選取的連接器。

:::image type="content" source="media/connectors-selection-ui.png" alt-text="從頻道右上角的 [其他] 選項，將連接器新增到 Teams 中的頻道。":::

## <a name="update-url-of-a-connector"></a>更新連接器的 URL

Teams 連接器正在轉換為新的 URL，以增強安全性。 在轉換期間，您會收到更新已設定之連接器的通知。 請儘早更新您的連接器，以避免連接器服務中斷。 若要更新您的連接器：

1. 在連接器設定頁面中，檢查已設定之連接器旁是否有 **「需要注意」** 的訊息。

   :::image type="content" source="media/teams-attention-required-message.png" alt-text="「需要注意」訊息的螢幕擷取畫面。":::

1. 若要重新建立連入 Webhook 連接器的連線，請選取 **[更新 URL]** 然後使用已產生的 Webhook URL。

   :::image type="content" source="media/teams-update-url-option.png" alt-text="[更新 URL] 按鈕的螢幕擷取畫面。":::

1. 對於其他連接器類型，請移除連接器並重新建立連接器設定。 一則 **「URL 是最新的」** 訊息會出現。 

   :::image type="content" source="media/teams-url-updated.png" alt-text="「URL 是最新的」訊息之螢幕擷取畫面。":::

## <a name="related-articles"></a>相關文章

* [自訂連接器和 Webhook 概觀](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)
* [建立 Office 365 連接器](/microsoftteams/platform/webhooks-and-connectors/how-to/connectors-creating)
