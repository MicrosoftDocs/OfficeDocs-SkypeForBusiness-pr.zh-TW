---
title: 使用 Microsoft 365 和自訂連接器
author: LolaJacobsen
ms.author: lolaj
manager: serdars
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
ms.openlocfilehash: 33a407de891f0d988b1fb32988556059c6adc2e0
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2020
ms.locfileid: "43778589"
---
<a name="use-microsoft-365-and-custom-connectors-in-microsoft-teams"></a>在 Microsoft 團隊中使用 Microsoft 365 和自訂連接器
=======================================================

連接器可將經常使用的內容和服務更新直接傳送到頻道，讓您的團隊保持在最新狀態。 透過連接器，您的 Microsoft 團隊使用者可以在其團隊的聊天串流內，從 Twitter、Trello、Wunderlist、GitHub 以及 Azure DevOps 服務等流行服務接收更新。

如果小組許可權允許，小組中的任何成員都可以將其小組與流行的雲端服務連線，而且所有小組成員都會收到來自該服務的活動通知。 連接器在最初設定連接器的成員已離開之後，仍能繼續運作。 任何擁有 add\remove 許可權的小組成員都可以修改其他成員的連接器設定。

Microsoft 365 連接器可搭配 Microsoft 團隊和 Microsoft 365 群組使用，讓所有成員都能更輕鬆地保持同步並快速接收相關資訊。 Microsoft 團隊和 Exchange 都使用相同的連接器模型，這可讓您在這兩個平臺中使用相同的連接器。 不過，請注意，針對小組所依賴的 Office 365 群組停用連接器，也會停用為該小組建立連接器的能力。

<a name="add-a-connector-to-a-channel"></a>在頻道中新增連接器
----------------------------

目前，您可以使用 Microsoft 團隊桌面與網頁用戶端來新增連接器。 不過，您可以在**所有用戶端**（包括行動裝置）上查看透過這些連接器發佈的資訊。

1. 若要新增連接器至頻道，請按一下頻道名稱右側的**省略號（...）** ，然後按一下 [**連接器**]。

    ![已選取 [連接器] 選項的 [小組介面] 螢幕擷取畫面。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2. 您可以從各種可用的連接器中進行選取，然後按一下 [**新增**]。

    ![顯示可用連接器之 [連接器] 對話方塊的螢幕擷取畫面。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3. 填入所選連接器所需的資訊，然後按一下 [**儲存**]。 每個連接器都需要一組不同的資訊才能正常運作，而某些可能需要您使用連接器設定頁面上提供的連結登入服務。

    ![RSS 連接器之 [設定] 頁面的螢幕擷取畫面。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4. 連接器所提供的資料會自動發佈到頻道。

    ![[團隊] 介面的螢幕擷取畫面，顯示頻道中的交談。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<a name="develop-custom-connectors"></a>開發自訂連接器
----------------------------

您也可以建立自訂連接器，以及接收和外寄 webhooks。 如需詳細資訊，請參閱我們的[開發人員文件](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)。
