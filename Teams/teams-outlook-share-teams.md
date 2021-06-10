---
title: 共用至Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
localization_priority: Normal
search.appverid: MET150
description: 瞭解共用至Teams功能，讓使用者從 Outlook 共用電子郵件和電子郵件附件至任何聊天或頻道Teams。
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: af5c2f6029b0c5314c507de7734abf8c479af709
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098219"
---
# <a name="share-to-teams-from-outlook"></a>從 Teams 共用Outlook

從 Teams 共用到Outlook (共用Teams) 讓使用者共用電子郵件 ，包括附件Outlook到任何聊天或頻道Teams。

## <a name="outlook-add-in-for-share-to-teams"></a>Outlook共用至Teams 

共用至Teams功能需要一個適用于 Outlook 的Outlook。 每當使用者以 Web 應用程式或桌面用戶端Teams時，系統就會自動Teams此附加元件。

> [!NOTE]
> 請務必在[Exchange Online](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)的 Outlook 用戶端Exchange Online 和用戶端存取規則中檢查[](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)Outlook 的附加元件。 此外，停用已連接體驗可能會防止Outlook的附加元件正常運作。 請參閱[在 Office](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c)中連接體驗以瞭解更多資訊。  

共用至Teams使用與使用者以電子郵件傳送頻道時相同的傳輸機制。 若要共用至聊天， (電子郵件附件) 電子郵件附件會複製到寄件者OneDrive。 若要共用至頻道，電子郵件和附件會複製到 SharePoint 中的電子郵件SharePoint。

Outlook 共用至 Teams 的附加元件會使用需求集 1.7，如[Outlook](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)的附加元件檔所詳述，其中包含 Outlook 附加元件的詳細資料、Outlook 附加元件的環境需求，以及需求集 1.7 支援的特定 Outlook 用戶端。

## <a name="enabling-or-disabling-share-to-teams"></a>啟用或停用共用至Teams

您可以Outlook PowerShell Cmdlet 選擇性地停用或啟用共用至Teams的附加元件。

> [!NOTE]
> 只有在安裝該附加元件之後，才能停用該附加元件。 如果您想要針對租使用者中的所有使用者強制執行停用，請定期執行腳本。

若要停用共用用來Outlook的Teams，請執行[此處找到的 Cmdlet。](/powershell/module/exchange/disable-app?view=exchange-ps) 

若要啟用 Share 用來Outlook的Teams，請執行[此處找到的 Cmdlet。](/powershell/module/exchange/enable-app?view=exchange-ps)

## <a name="browsers-and-single-sign-on"></a>瀏覽器和單一登入

共用至Teams，無論是網頁Outlook或桌面Outlook用戶端，都仰賴瀏覽器 WebView。 請參閱[應用程式Office](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins)所使用的瀏覽器，以瞭解有關哪些用戶端使用特定瀏覽器的詳細資訊。 

> [!IMPORTANT]
> 共用至Teams使用者瀏覽器必須同時啟用協力廠商 Cookie 和本地儲存空間存取。

共用Teams使用單一登入 (SSO) ，這表示使用者在透過共用至Teams 時不需要提供其認證。 網頁Outlook SSO 預設支援並回復 https://outlook.office365.com/owa/extSSO.aspx https://outlook.office.com/owa/extSSO.aspx URL。 對於虛名網域，系統管理員必須新增適當的Azure Active Directory URL。