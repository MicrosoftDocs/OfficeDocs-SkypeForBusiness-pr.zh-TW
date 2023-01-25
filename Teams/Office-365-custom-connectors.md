---
title: 管理 Microsoft 365 連接器和自訂連接器
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
audience: admin
ms.date: 01/24/2023
ms.collection:
- M365-collaboration
ms.reviewer: lucarras
search.appverid: MET150
f1.keywords:
- NOCSH
description: 瞭解連接器如何經常將內容和更新直接傳送到 Teams 頻道，讓您的團隊持續更新，以供您使用的服務使用。
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: bf38711da0205e7c674e769942d00d340d51f66e
ms.sourcegitcommit: 1cb5f7129562eb2b228da23497c0e09e53da3872
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2023
ms.locfileid: "69983681"
---
# <a name="manage-microsoft-365-connectors-and-custom-connectors"></a>管理 Microsoft 365 連接器和自訂連接器

Microsoft Teams 中的連接器會直接從協力廠商服務將內容和服務更新傳送到 Teams 頻道。 使用者會使用連接器，從 Trello、Wunderlist、GitHub 和 Azure DevOps Services 等熱門服務接收更新。 更新會直接張貼到聊天串流中。 這可讓所有成員輕鬆保持同步，並快速收到相關資訊。

Microsoft 365 連接器同時用於 Teams 和 Microsoft 365 群組。 您可以在 Teams 和 Microsoft Exchange 中使用相同的連接器。 

<!--- However, if you disable any connectors configured for a Microsoft 365 group, it also disables the ability for the Microsoft 365 group to create connectors. --->

如果團隊許可權允許，團隊中的任何成員都可以在團隊中新增連接器，而且所有小組成員都會收到來自該服務的活動通知。 任何具有新增或移除權限的小組成員都可以修改其他成員的連接器設定。

## <a name="enable-or-disable-connectors-in-teams"></a>在 Teams 中啟用或停用連接器

Exchange Online PowerShell v2 模組使用新式驗證，並搭配多重要素驗證 (MFA) 連線至 Microsoft 365 中所有 Exchange 相關 PowerShell 環境。 系統管理員可以使用 Exchange Online PowerShell 來停用整個租用戶或特定群組信箱的連接器，這會影響該租用戶或信箱中的所有使用者。 無法針對少數特定使用者停用。

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

## <a name="considerations-when-using-connectors-in-teams"></a>在 Teams 中使用連接器時的考慮

* 在政府雲端社群 (GCC) 環境中，連接器會根據預設定為停用。 若要啟用這些參數，請使用 `SetOrganizationConfig` Cmdlet 將 `ConnectorsEnabled` 或 `ConnectorsEnabledForTeams` 參數設定為 `$true`。 連線到 [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps&preserve-view=true)。

* 如果將連接器新增至團隊的使用者離開團隊，連接器會繼續運作。

* 下列連接器自 2023 年 1 月起不提供使用：

  * 哈哈
  * AIRBRAKE
  * AIRCALL
  * APPLINKS
  * APPSIGNAL
  * 青苗
  * BITBUCKET
  * BITBUCKETSERVER
  * 夥計
  * BUGSNAG
  * BUILDKITE
  * CATSONE
  * CHATRA
  * CIRCLECI
  * CODESHIP
  * GETRESPONSE
  * GHOSTINSPECTOR
  * 槽
  * HEROKU
  * HONEYBADGER
  * 對講機
  * LOGENTRIES
  * NEWRELIC
  * OPSGENIE
  * PAGERDUTY
  * PAPERTRAIL
  * PINGDOM
  * TRACKTRACKER
  * RAYGUN
  * ROLLBAR
  * RUNSCOPE
  * SATISMETER
  * 信號
  * 哨兵
  * SHAREPOINT。
  * SIMPLEINOUT
  * STATUSPAGEIO
  * 顛覆
  * TEAMFOUNDATIONSERVER
  * TESTFAIRY
  * TRAVISCI
  * UPDOWN
  * USERLIKE
  * XPDEV

## <a name="related-articles"></a>相關文章

* [自訂連接器和網路任務的概觀](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)
* [如何建立連接器Office 365](/microsoftteams/platform/webhooks-and-connectors/how-to/connectors-creating)
