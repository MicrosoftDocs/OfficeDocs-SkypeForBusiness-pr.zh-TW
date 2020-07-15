---
title: 在 Microsoft 團隊中共用檔案
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: haagaraw
audience: admin
search.appverid: MET150
description: 瞭解 Microsoft 團隊中的檔案共用體驗。
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 98935f7d8629e22b733b12f3f046ccb7af36b396
ms.sourcegitcommit: 70b80892a152f86a6d596f0f5b58cf391bc29098
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2020
ms.locfileid: "45138332"
---
# <a name="sharing-files-in-microsoft-teams"></a>在 Microsoft 團隊中共用檔案

在 Microsoft 團隊中，使用者可以與組織內部和外部的其他團隊使用者共用內容。 [在小組中共用] 是以 SharePoint 和 OneDrive 中所設定的設定為基礎，因此您針對 SharePoint 和 OneDrive 設定的任何內容，都會同時控制小組中的共用功能。

## <a name="overview"></a>概觀

使用者可以從 OneDrive、他們有權存取的小組和網站，以及從他們的電腦上共用檔案。 若要共用檔案，使用者可以執行下列動作：

- 在頻道中，按一下 [**附加**] （曲別針圖示）、選取 [**最近** **]、[流覽團隊和頻道]、[** **OneDrive**] 或 [**從我的電腦上傳**]，然後選擇他們要共用的檔案。 <br> 
    ![螢幕擷取畫面顯示如何從頻道共用檔案](media/share-files-channel.png)
- 在聊天中，按一下 [**附加**] （曲別針圖示），選取或 [ **OneDrive** ] 或 [**從我的電腦上傳**]，然後選擇他們要共用的檔案。 <br>
    ![螢幕擷取畫面顯示如何從聊天共用檔案](media/share-files-chat.png)
- 在撰寫方塊中複製並貼上共用連結。<br>
    ![螢幕擷取畫面顯示撰寫方塊中的檔案預覽](media/share-files-link.png)

### <a name="what-you-need-to-know-about-the-file-sharing-experience"></a>檔案共用體驗所需注意的事項

### <a name="permissions-of-shared-files-and-sharing-links"></a>共用檔案和共用連結的許可權

當使用者透過在 OneDrive 或團隊和頻道中流覽來共用檔案時，系統會向所有收件者授與[組織層級所設定的預設許可權](https://docs.microsoft.com/sharepoint/change-default-sharing-link)。

當使用者複製並貼上共用連結時，該共用連結上所設定的許可權即會生效，SharePoint URL 會縮短為檔案名。 換句話說，小組只會使用檔案名來連結至檔案。

當使用者在團隊中共用檔案時，他們可以設定誰可以存取該檔案，就像在 Microsoft 365 中一樣。 他們可以為您組織中的人員、擁有現有存取權的人員或特定人員（可在1:1 聊天、群組聊天或頻道中加入人員）提供存取權。  共用檔案時，會在郵件中提供檔案預覽，以及**開啟 [線上**]、[**下載**] 和 [**複製連結**] 等所有檔案動作。 根據預設，檔案會在 [團隊] 中開啟。 有時候，共用連結可能不會在使用者傳送郵件時轉換成檔案預覽。 系統會產生檔案預覽，但在這種情況下，不會將共用連結截短至唯一的檔案名。

當使用者在聊天或頻道中共用檔案時，系統會通知您是否有部分或所有收件者沒有許可權來查看檔案。 他們可以在共用檔案前，按一下現在出現在郵件中的檔案預覽旁邊的箭號，即可變更該檔案的許可權。

![如果收件者沒有許可權，螢幕擷取畫面顯示通知](media/share-files-permissions.png)

### <a name="copy-a-sharing-link-in-teams"></a>複製小組中的共用連結

使用者可以複製 SharePoint 共用連結，並變更共用許可權，就像在 Microsoft 365 中一樣。 他們可以授與您組織中的人員、擁有現有存取權的人員，或特定人員的存取權。 連結的預設許可權會與組織階層的預設許可權集相同，除非 SharePoint 網站層級許可權覆蓋它。

## <a name="configure-sharing-in-onedrive-and-sharepoint"></a>在 OneDrive 和 SharePoint 中設定共用

如需在 OneDrive 和 SharePoint 中共用檔案的詳細資訊，包括如何設定共用，以及如何開啟和關閉共用，請參閱：

- [[外部共用] 概覽](https://docs.microsoft.com/sharepoint/external-sharing-overview)-說明使用者共用時所發生的情況，視其共用和人員的情況而定。

- [管理共用設定](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off)-說明全域和 SharePoint 系統管理員可以如何變更其組織層級的 SharePoint 和 OneDrive 共用設定。

- [開啟或關閉網站的外部共用](https://docs.microsoft.com/sharepoint/change-external-sharing-site)–說明全域和 SharePoint 系統管理員可以如何開啟或關閉網站的外部共用。

- [變更網站的預設連結類型](https://docs.microsoft.com/sharepoint/change-default-sharing-link)-說明如何設定預設連結類型，讓它更具限制性。

## <a name="more-information"></a>詳細資訊

- [SharePoint Online 與商務用 OneDrive 與 Microsoft 團隊互動的方式](sharepoint-onedrive-interact.md)

- [SharePoint 與團隊：更緊密地合作](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)

- [共用 OneDrive 檔案和資料夾](https://support.office.com/article/Share-OneDrive-files-and-folders-9fcc2f7d-de0c-4cec-93b0-a82024800c07#OS_Type=OneDrive_-_Business)

- [共用 SharePoint 檔案或資料夾](https://support.office.com/article/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c)
