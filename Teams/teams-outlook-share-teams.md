---
title: 共用至Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: 瞭解共用至Teams功能，讓使用者從 Outlook 共用電子郵件和電子郵件附件至 Teams。
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ebbfeecf72be2d042e3686d11be98d3343a3d5f4
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58633977"
---
# <a name="share-to-teams-from-outlook"></a>從 Teams 共用Outlook

從 Teams 共用Outlook (共用至 Teams) 可讓使用者共用電子郵件 ，包括附件Outlook到 Teams 中的任何聊天或頻道。

## <a name="outlook-add-in-for-share-to-teams"></a>Outlook共用至共用Teams 

共用至Teams功能需要適用于 Outlook。 每當使用者以 Web 應用程式或桌面用戶端Teams時，就會自動安裝Teams。

> [!NOTE]
> 請務必在 Outlook [](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) Exchange Online 和[Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)中的用戶端存取規則中檢查適用于 Outlook 的附加元件。 此外，停用連接體驗可能會防止Outlook的附加元件正常運作。 請參閱[在 Office](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c)中連接體驗以瞭解更多資訊。  

共用至Teams使用與使用者傳送頻道電子郵件時相同的傳輸機制。 若要共用至聊天， (電子郵件附件) 電子郵件附件會複製到寄件者OneDrive。 若要共用至頻道，電子郵件和附件會複製到 SharePoint 中的電子郵件SharePoint。

Outlook 共用至 Teams 的附加元件會使用需求集 1.7，如[Outlook](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)的附加元件檔所詳述，其中包含 Outlook 附加元件的詳細資料、Outlook 附加元件的環境需求，以及需求集 1.7 支援的特定 Outlook 用戶端。

## <a name="enabling-or-disabling-share-to-teams"></a>啟用或停用共用至Teams

您可以使用Outlook PowerShell Cmdlet 選擇性地停用或啟用共用至Teams的附加元件。

> [!NOTE]
> 只有在安裝該附加元件之後，才能停用該附加元件。 如果您想要針對租使用者中的所有使用者強制執行停用，請定期執行腳本。

若要停用 Share 用來Outlook的Teams，請執行[此處找到的 Cmdlet。](/powershell/module/exchange/disable-app?view=exchange-ps) 

若要啟用 Share 用來Outlook的Teams，請執行[此處找到的 Cmdlet。](/powershell/module/exchange/enable-app?view=exchange-ps)

## <a name="browsers-and-single-sign-on"></a>瀏覽器和單一登入

在桌面Teams和Outlook 網頁版Outlook共用至用戶端，都仰賴瀏覽器 WebView。 請參閱[應用程式Office](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins)使用的瀏覽器，以瞭解有關哪些用戶端使用特定瀏覽器的詳細資訊。 

> [!IMPORTANT]
> 共用Teams使用者瀏覽器必須同時啟用協力廠商 Cookie 和本地儲存空間存取。

共用Teams使用單一登入 (SSO) ，這表示使用者在透過共用至 Teams 使用該附加元件時不需要提供認證。 SSO Outlook 網頁版 https://outlook.office365.com/owa/extSSO.aspx https://outlook.office.com/owa/extSSO.aspx 預設支援並回復 URL。 對於虛名網域，系統管理員需要新增適當的Azure Active Directory URL。