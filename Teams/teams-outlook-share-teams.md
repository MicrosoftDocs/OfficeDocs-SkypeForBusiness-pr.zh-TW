---
title: 分享給Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: 瞭解 [共用至Teams] 功能，此功能可讓使用者從Outlook共用電子郵件和電子郵件附件至Teams中的任何聊天或頻道。
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2a768424033ff300a079fc0b505d1e9ce32a970e
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2022
ms.locfileid: "65682024"
---
# <a name="share-to-teams-from-outlook"></a>從 Outlook 分享至Teams

從 Outlook (Share 到 Teams) 分享至Teams可讓使用者從Outlook共用電子郵件，包括附件至Teams中的任何聊天或頻道。

## <a name="outlook-add-in-for-share-to-teams"></a>Outlook [共用] 增益集Teams 

[共用至Teams] 功能需要增益集才能Outlook。 每當使用者登入 Teams Web 應用程式或Teams桌面用戶端時，就會自動安裝此增益集。

> [!NOTE]
> 請務必檢閱[Exchange Online 中Exchange Online](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)和用戶端[存取規則中的Outlook](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)增益集，以確保Outlook的增益集正確運作。 此外，停用連線體驗也可能會使Outlook的增益集無法正常運作。 如需詳細資訊，請參閱[Office中的連線體驗](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c)。  

分享給Teams使用與使用者傳送頻道電子郵件時相同的傳輸機制。 若要共用至聊天，電子郵件 (包括電子郵件附件) 會複製到寄件者的OneDrive。 若要共用至頻道，電子郵件和附件會複製到 SharePoint 中的 [**電子郵件]** 資料夾。

Outlook增益集檔中詳述的 [共用至Teams的[Outlook加](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)載宏] 使用需求集 1.7，其中包含Outlook增益集的詳細資料、Outlook增益集的環境需求，以及需求設定 1.7 所支援的特定Outlook用戶端。

## <a name="enabling-or-disabling-share-to-teams"></a>啟用或停用 [共用] 以Teams

您可以使用下列 PowerShell Cmdlet 選擇性地停用或啟用 [共用至Teams] 的Outlook增益集。

> [!NOTE]
> 只有在安裝增益集之後，才能停用增益集。 如果您想要強制停用租使用者中的所有使用者，請定期執行腳本。

若要停用分享至Teams所用Outlook增益集，請[執行此處找到的 Cmdlet](/powershell/module/exchange/disable-app)。

若要啟用 [共用] 用來Teams Outlook增益集，請[執行此處找到的 Cmdlet](/powershell/module/exchange/enable-app)。

## <a name="browsers-and-single-sign-on"></a>瀏覽器和單一登入

共用至Teams，無論是Outlook 網頁版還是Outlook桌面用戶端，都仰賴瀏覽器 WebView。 如需用戶端使用哪些特定瀏覽器的詳細資料，請參閱[Office增益集使用的](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins)瀏覽器。 

> [!IMPORTANT]
> 共用至Teams要求使用者的瀏覽器必須同時啟用協力廠商 Cookie 和本機儲存空間存取。

共用至Teams使用單一登入 (SSO) ，這表示使用者在透過 [分享至Teams] 使用增益集時不需要提供認證。 根據預設，Outlook 網頁版 SSO 支援 <https://outlook.office365.com/owa/extSSO.aspx> 及 <https://outlook.office.com/owa/extSSO.aspx> 回復 URL。 對於虛名網域，系統管理員必須新增適當的Azure Active Directory回復 URL。
