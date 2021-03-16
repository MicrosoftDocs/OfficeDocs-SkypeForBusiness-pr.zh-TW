---
title: 共用至 Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
localization_priority: Normal
search.appverid: MET150
description: 瞭解共用至 Teams 功能，讓使用者從 Outlook 共用電子郵件和電子郵件附件至 Teams 中任何聊天或頻道。
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 80882bddae434b66f6a3e5988c08474859b37861
ms.sourcegitcommit: c6b630f9193d7f82f0416bd567a1de390d4b260f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819431"
---
# <a name="share-to-teams-from-outlook"></a>從 Outlook 共用至 Teams

從 Outlook 共用至 Teams (共用至 Teams) 可讓使用者共用電子郵件 ，包括附件，從 Outlook 共用至 Teams 中任何聊天或頻道。

## <a name="outlook-add-in-for-share-to-teams"></a>共用至 Teams 的 Outlook 附加元件 

共用至 Teams 功能需要 Outlook 的附加元件。 每當使用者登錄 Teams Web App 或 Teams 桌面用戶端時，就會自動安裝此附加元件。

> [!NOTE]
> 請務必檢查 Exchange Online 中的 [Outlook](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) 附加元件和 Exchange Online 中的 [用戶端](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) 存取規則，以確保 Outlook 的附加元件正確運作。 此外，停用連接體驗可能會防止 Outlook 的附加元件正常運作。 請參閱 [Office 中的已連接](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) 體驗以瞭解更多資訊。  

共用至 Teams 會使用與使用者以電子郵件傳送頻道時相同的傳輸機制。 若要共用至聊天， (電子郵件附件) 電子郵件附件會複製到寄件者的 OneDrive。 若要共用至頻道，電子郵件和附件會複製到 SharePoint 中的電子郵件訊息資料夾。

共用至 Teams 的 Outlook 附加元件會使用需求集 1.7，如 [Outlook](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)附加元件檔所詳述，其中包含 Outlook 附加元件的詳細資料、Outlook 附加元件的環境需求，以及需求集 1.7 支援的特定 Outlook 用戶端。

## <a name="enabling-or-disabling-share-to-teams"></a>啟用或停用 Teams 共用

您可以使用下列 PowerShell Cmdlet，選擇性地針對每個使用者停用或啟用共用至 Teams 的 Outlook 附加元件。

> [!NOTE]
> 只有在安裝該附加元件之後，才能停用該附加元件。 如果您想要針對租使用者中的所有使用者強制執行停用，請定期執行腳本。

若要停用共用至 Teams 所使用的 Outlook 附加元件，請執行[此處找到的 Cmdlet。](https://docs.microsoft.com/powershell/module/exchange/disable-app?view=exchange-ps) 

若要啟用 Share to Teams 所使用的 Outlook 附加元件，請執行[此處找到的 Cmdlet。](https://docs.microsoft.com/powershell/module/exchange/enable-app?view=exchange-ps)

## <a name="browsers-and-single-sign-on"></a>瀏覽器和單一登入

在 Outlook 網頁版和 Outlook 桌面用戶端中，共用至 Teams 仰賴瀏覽器 WebView。 請參閱 [Office 附加元件](https://docs.microsoft.com/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) 使用的瀏覽器，瞭解哪些用戶端使用哪些特定瀏覽器的詳細資訊。 

> [!IMPORTANT]
> 共用至 Teams 時，使用者瀏覽器必須同時啟用協力廠商 Cookie 和本地儲存空間存取。

共用至 Teams 使用單一登入 (SSO) ，這表示使用者在透過共用至 Teams 使用該附加元件時，不需要提供認證。 Outlook 網頁用 SSO 預設支援並回復 https://outlook.office365.com/owa/extSSO.aspx https://outlook.office.com/owa/extSSO.aspx URL。 對於虛名網域，系統管理員必須新增適當的 Azure Active Directory 回復 URL。