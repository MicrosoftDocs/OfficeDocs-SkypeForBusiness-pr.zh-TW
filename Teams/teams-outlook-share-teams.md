---
title: 共用至 Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: 瞭解 [共用至 Teams] 功能，此功能可讓使用者從 Outlook 共用電子郵件和電子郵件附件到 Teams 中的任何聊天或頻道。
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e2ac9a38e16000829b391e77dffdd718ed349299
ms.sourcegitcommit: f5546acf02ec644225f6d0fb41f38b1912da6adf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/21/2022
ms.locfileid: "66952757"
---
# <a name="share-to-teams-from-outlook"></a>從 Outlook 共用至 Teams

從 Outlook 共用至 Teams ([共用至 Teams]) 可讓使用者從 Outlook 共用電子郵件，包括附件至 Teams 中的任何聊天或頻道。

## <a name="outlook-add-in-for-share-to-teams"></a>共用至 Teams 的 Outlook 增益集 

[共用至 Teams] 功能需要 Outlook 的增益集。 每當使用者登入 Teams Web 應用程式或 Teams 桌面用戶端時，就會自動安裝此增益集。

> [!NOTE]
> 請務必檢閱[Exchange Online 中的 Outlook 載入](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)宏和[Exchange Online 中的用戶端存取規則](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)，以確保 Outlook 的增益集正確運作。 此外，停用連線體驗也會導致 Outlook 的增益集無法正常運作。 如需詳細資訊，請參閱 [Office 中的連線體驗](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) 。 增益集不支援共用信箱。 

[共用至 Teams] 使用與使用者傳送頻道電子郵件時相同的傳輸機制。 若要共用至聊天，系統會將包含電子郵件附件) 的電子郵件 (複製到寄件者的 OneDrive。 若要共用至頻道，電子郵件和附件會複製到 SharePoint **中的Email郵件** 資料夾。

[共用至 Teams] 的 Outlook 增益集使用需求集 1.7，如 [Outlook 增益集檔所](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)詳述，其中包含 Outlook 增益集的詳細資料、Outlook 增益集的環境需求，以及需求設定 1.7 所支援的特定 Outlook 用戶端。

## <a name="enabling-or-disabling-share-to-teams"></a>啟用或停用 [共用至 Teams]

您可以使用下列 PowerShell Cmdlet，選擇性地停用或針對個別使用者啟用 [共用至 Teams] 的 Outlook 增益集。

> [!NOTE]
> 只有在安裝增益集之後，才能停用增益集。 如果您想要強制停用租使用者中的所有使用者，請定期執行腳本。

若要停用 [共用至 Teams] 所使用的 Outlook 增益集，請執行 [此處找到的 Cmdlet](/powershell/module/exchange/disable-app)。

若要啟用 [共用至 Teams] 所使用的 Outlook 增益集，請執行 [此處找到的 Cmdlet](/powershell/module/exchange/enable-app)。

## <a name="browsers-and-single-sign-on"></a>瀏覽器和單一登入

在 Outlook 網頁版 和 Outlook 桌面用戶端中共用至 Teams，需仰賴瀏覽器 WebView。 如需用戶端使用哪些特定瀏覽器的詳細資料，請參閱 [Office 增益集使用的](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) 瀏覽器。 

> [!IMPORTANT]
> 共用至 Teams 時，使用者的瀏覽器必須同時啟用協力廠商 Cookie 和本機儲存空間存取。

共用至 Teams 會使用單一登入 (SSO) ，這表示使用者在透過 [共用至 Teams] 使用增益集時，不需要提供認證。 根據預設，Outlook 網頁版 SSO 支援 <https://outlook.office365.com/owa/extSSO.aspx> 及 <https://outlook.office.com/owa/extSSO.aspx> 回復 URL。 對於虛名網域，系統管理員必須新增適當的 Azure Active Directory 回復 URL。
