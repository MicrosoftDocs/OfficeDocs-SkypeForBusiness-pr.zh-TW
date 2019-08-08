---
title: 在 Microsoft 團隊中進行 eDiscovery 調查內容
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/12/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
description: 瞭解當您需要提交以電子形式儲存的法律訴訟資訊時, 要採取的動作。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6831ec2cef16e65e2fd8dd722d436c12b7548a5c
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236809"
---
<a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>在 Microsoft 團隊中進行 eDiscovery 調查內容
============================

大型企業通常會面臨大量要求提交所有以電子方式儲存資訊 (ESI) 的法律訴訟。

所有團隊1:1 或群組聊天都會在各個使用者的信箱中進行歸檔, 而所有通道訊息都會在代表小組的群組信箱中傳送。 上傳的檔案包含在 SharePoint Online 和商務用 OneDrive 的 eDiscovery 功能底下。

1.  若要使用 Microsoft 團隊內容進行 eDiscovery 調查, 請參閱[此](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da)連結中的步驟1。

2.  Microsoft 團隊資料會以 IM 或交談的方式顯示在 Excel eDiscovery 匯出輸出中, 而且您可以裝載。[PST] (Outlook) 來查看匯出後的郵件。

    裝載時。針對團隊的 PST, 請注意, 所有交談都會保留在 [交談記錄] 底下的 [小組聊天] 資料夾中。 郵件標題會對應到 [小組] 和 [頻道]。 從 [查看] 下方的影像, 您可以看到來自 Bob 的訊息, messaged 製造規格小組的專案7頻道。

    ![Outlook 中使用者信箱的小組聊天資料夾螢幕擷取畫面](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

3.  若要查看使用者信箱中的私人聊天, 他們也位於 [交談歷程記錄] 底下的 [小組聊天] 資料夾內。

## <a name="ediscovery-of-guest-to-guest-chats"></a>電子檔探索訪客與來賓聊天

若沒有信箱, 來賓對訪客的聊天 (沒有家用租使用者的1xN 聊天) 就不會被編制索引, 因此也不會包含在 eDiscovery 中。 若要協助電子檔探索以進行來賓對訪客聊天, 會建立一個雲端信箱 (或幻影信箱) 來儲存1xN 資料。 在將團隊聊天資料儲存在雲端型信箱之後, 就會針對 eDiscovery 與合規性內容搜尋編制索引。

下圖顯示 eDiscovery 如何針對沒有信箱的來賓對訪客聊天進行運作。

![來賓-訪客-聊天-無信箱](media/conduct-an-ediscovery-investigation-of-content-in-microsoft-teams-image2.png)
