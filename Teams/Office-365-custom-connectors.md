---
title: 管理Microsoft 365和自訂連接器
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
description: 連接器透過將您經常使用的服務中的內容和更新直接發送到頻道中，進而使您的團隊保持最新狀態。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 100db95adf900a48898515b9bb9a3a753b47de4f
ms.sourcegitcommit: d16fb01f752d186445893ea8e3b0d4450a4a0e67
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/29/2022
ms.locfileid: "65125438"
---
# <a name="manage-microsoft-365-and-custom-connectors"></a>管理Microsoft 365和自訂連接器

為了持續更新您的小組，連接器會將常用的內容和服務更新直接傳送到Teams通道。 透過連接器，您的Teams使用者可以從 Trello、Wunderlist、GitHub 和 Azure DevOps Services 等熱門服務接收更新。 更新會直接張貼到小組中的聊天串流中。

Microsoft 365連接器同時搭配Microsoft Teams和Microsoft 365群組使用，可讓所有成員更輕鬆地保持同步，並快速接收相關資訊。 Microsoft Teams和Exchange都使用相同的連接器模型，這可讓您在兩個平臺中使用相同的連接器。 不過，如果您停用為Microsoft 365組設定的任何連接器，也會停用Microsoft 365群組建立連接器的功能。

如果團隊許可權允許，團隊中的任何成員都可以使用連接器將小組連線到熱門的雲端服務，而且所有小組成員都會收到來自該服務的活動通知。 最初設定連接器的成員已離開之後，連接器仍會繼續運作。 任何具有新增或移除許可權的小組成員都可以修改其他成員設定的連接器。

## <a name="enable-or-disable-connectors-in-teams"></a>啟用或停用 Teams 中的連接器

Exchange Online PowerShell V2 模組使用新式驗證，並可與稱為 MFA 的多重要素驗證搭配使用，以連線至 Microsoft 365 中所有Exchange相關 PowerShell 環境。 系統管理員可以使用 Exchange Online PowerShell 來停用整個租使用者或特定群組信箱的連接器，這會影響該租使用者或信箱中的所有使用者。 無法針對少數特定使用者停用。 此外，政府社群雲端的連接器預設為停用，稱為GCC租使用者。

租使用者設定會覆寫群組設定。 例如，如果系統管理員為群組啟用連接器，並在租使用者上停用連接器，群組的連接器就會停用。 若要在 Teams 中啟用連接器，請使用包含或不含 MFA 的新式驗證連線[至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps#connect-to-exchange-online-powershell-using-modern-authentication-with-or-without-mfa&preserve-view=true)。

### <a name="commands-to-enable-or-disable-connectors"></a>啟用或停用連接器的命令

在 Exchange Online PowerShell 中執行下列命令：

* 若要停用租使用者的連接器： `Set-OrganizationConfig -ConnectorsEnabled:$false` 。
* 若要停用租使用者可採取動作的訊息： `Set-OrganizationConfig -ConnectorsActionableMessagesEnabled:$false` 。
* 若要啟用Teams的連接器，請執行下列命令：
  * `Set-OrganizationConfig -ConnectorsEnabled:$true`
  * `Set-OrganizationConfig -ConnectorsEnabledForTeams:$true`
  * `Set-OrganizationConfig -ConnectorsActionableMessagesEnabled:$true`

如需 PowerShell 模組交換的詳細資訊，請參閱 [Set-OrganizationConfig](/powershell/module/exchange/Set-OrganizationConfig?view=exchange-ps&preserve-view=true)。 若要啟用或停用Outlook連接器，請[將應用程式連線至Outlook中的群組](https://support.microsoft.com/topic/connect-apps-to-your-groups-in-outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab)。

<!---TBD: Delete this section after customer migration to new Webhook URL is complete --->

#### <a name="connector-url-update-notification"></a>連接器 URL 更新通知

Teams連接器正在轉換到新的 URL 以加強安全性。 在轉換期間，您會收到更新已設定之連接器的通知。 請儘早更新您的連接器，以防止任何對連接器服務的干擾。 若要更新連接器：

1. 在 [連接器設定] 頁面上，核取設定的連接器旁的 [ **注意必要** ] 訊息。

   ![[注意必要] 訊息的螢幕擷取畫面。](media/Teams_Attention_Required_message.png)

1. 若要重新建立內送 webhook 連接器的連線，請選取 **[更新 URL** ]，然後使用產生的 webhook URL。

   ![[更新 URL] 按鈕的螢幕擷取畫面。](media/Teams_update_URL_button.png)

1. 對於其他連接器類型，請移除連接器並重新建立連接器設定。 系統會顯示最新訊息的 **URL** 。

   ![URL 是最新郵件的螢幕擷取畫面。](media/Teams_URL_up_to_date.png)

## <a name="see-also"></a>另請參閱

* [自訂連接器和網路任務概觀](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)
* [建立Office 365連接器](/microsoftteams/platform/webhooks-and-connectors/how-to/connectors-creating)