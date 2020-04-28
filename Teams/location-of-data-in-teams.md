---
title: Microsoft 團隊中的資料位置
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: anach, kehardy
description: 在本文中，您將瞭解在 Microsoft 團隊中，資料位於地理位置的位置。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ebe94c04fcc4d93f636544d54930cf83855deec2
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904815"
---
# <a name="location-of-data-in-microsoft-teams"></a>Microsoft 團隊中的資料位置

團隊中的資料位於與您的 Office 365 組織相關聯的地理區域中。 目前，團隊支援澳大利亞、加拿大、法國、德國、印度、日本、南非、韓國、瑞士（包括列支敦斯登）、阿拉伯聯合大公國、英國、美洲、APAC 及 EMEA 地區。 

> [!IMPORTANT]
> 團隊目前在澳大利亞、加拿大、法國、德國、印度、日本、阿拉伯聯合大公國、英國、韓國、非洲和瑞士（包括列支敦斯登）等新的租使用者中提供資料。
> 新的租使用者定義為任何沒有租使用者登入團隊中的使用者的租使用者。 澳大利亞、印度、日本和韓國的現有租使用者將繼續將其小組資料儲存在 APAC 區域中。 加拿大中的現有租使用者將繼續將其資料儲存在美洲。 在華北、德國、列支敦斯登、阿拉伯聯合大公國、英國、南非和瑞士的現有租使用者，其資料會儲存在 EMEA 地區。

## <a name="where-your-teams-data-is-stored"></a>您的團隊資料的儲存位置

若要查看哪個地區駐留您租使用者的資料，請移至[Microsoft 365 系統管理中心](https://portal.office.com/adminportal/home) > **設定** > **組織設定檔**。 向下滾動至 [**資料位置**]。

![資料位置資料表的螢幕擷取畫面，其中包含系統管理中心的團隊](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="location-of-teams-data-at-rest"></a>[Rest] 上的小組資料位置

依內容類型而定，您的小組資料會以不同的方式儲存。 

![圖表顯示小組內容類型，以及將其儲存在其他位置](media/location-of-data-storage-at-rest.png)

請參閱[Microsoft 團隊結構上的 Ignite 專題討論會話](https://channel9.msdn.com/Events/Ignite/Microsoft-Ignite-Orlando-2017/BRK3071)，取得深入討論。

### <a name="core-teams-customer-data"></a>核心團隊客戶資料

如果您的租使用者是在澳大利亞、加拿大、歐洲同盟、法國、德國、印度、日本、南非、韓國、瑞士（包括列支敦斯登）、阿拉伯聯合大公國、英國或美國，Microsoft 將下列客戶資料儲存在該位置中：

- 團隊聊天、團隊和頻道交談、影像、語音信箱訊息及連絡人
- SharePoint Online 網站內容和儲存在該網站中的檔案
- 上傳到商務用 OneDrive 的檔案

#### <a name="chat-channel-messages-team-structure"></a>聊天、頻道訊息、團隊結構

團隊中的每個團隊都是由 Office 365 群組及其 SharePoint 網站和 Exchange 信箱來支援。 私人聊天（包括群組聊天）、在頻道中作為交談的一部分傳送的郵件，以及團隊和頻道的結構，都儲存在在 Azure 中執行的聊天服務中。 資料也會儲存在使用者和群組信箱的隱藏資料夾中，以啟用資訊保護功能。

#### <a name="voicemail-and-contacts"></a>語音信箱和連絡人

語音訊息儲存在 Exchange 中。 連絡人儲存在 Exchange 雲端資料儲存區中。 Exchange 與 Exchange 雲端儲存區已在每個全球資料中心 geos 中提供資料常駐功能。 針對所有團隊，語音信箱和連絡人都是儲存在美國國內、加拿大、法國、德國、印度、日本、阿拉伯聯合大公國、英國、南非、韓國、瑞士（包括列支敦斯登）及美國等。 針對所有其他國家/地區，檔案會根據租使用者關聯性儲存在美國、歐洲或亞太地區位置。

#### <a name="images-and-media"></a>影像和媒體

在聊天中使用的媒體（除了不會儲存的 Giphy Gif，但是原始 Giphy 服務 URL 的參照連結，Giphy 是非 Microsoft 服務）儲存在與聊天服務相同位置的 Azure 媒體服務中。

#### <a name="files"></a>檔案

在頻道中共用的檔案（包括 OneNote 和 Wiki）會儲存在小組的 SharePoint 網站上。 在會議或通話期間，在私人聊天或聊天中共用的檔案，會上傳並儲存在共用該檔案之使用者的商務用 OneDrive 帳戶中。 Exchange、SharePoint 和 OneDrive 已在每個全球資料中心 geos 提供資料常駐功能。 所以針對現有客戶，所有檔案、OneNote 筆記本、團隊 wiki 內容，以及屬於團隊經驗的信箱，都已儲存在根據您的租使用者關聯性的位置。 檔案是儲存在國內、加拿大、法國、德國、印度、日本、阿拉伯聯合大公國、英國、南非、韓國和瑞士（包括列支敦斯登）的國家/地區。 針對所有其他國家/地區，檔案會根據租使用者關聯性儲存在美國、歐洲或亞太地區的位置。

### <a name="datacenter-locations"></a>資料中心位置

本節所述的小組服務將資料儲存在下列位置：

|國家或地區  |資料中心位置 |
|---------|---------|
|澳洲   |新的南威爾士及維多利亞         |
|加拿大    |魁北克城市和多倫多         |
|法國    |Marseille 和巴黎         |
|德國    |柏林與 Frankfurt      |
|印度   |Chennai 和 Pune        |
|日本    |東京（Saitama）和 Osaka         |
|列支敦斯登   |Geneva 和蘇黎世       |
|南非     |Johannesburg 和維德角         |
|南韓     |首爾與 Busan         |
|瑞士    |Geneva 和蘇黎世       |
|阿拉伯聯合大公國     |阿布達比 Dhabi 和 Dubai         |
|英國     | Cardiff 和倫敦        |
|美洲–北和南部（AMER） |Bay、CA 與 Boydton、佛吉尼亞       |
|亞太地區（APAC）  |新加坡與香港        |
|歐洲、中東及亞洲（EMEA）   |都柏林與阿姆斯特丹        |

> [!NOTE]
> 對於列支敦斯登，資料會儲存在 Geneva 和蘇黎世的瑞士資料中心中的 [其他]。

### <a name="data-stored-with-a-third-party-storage-provider"></a>與協力廠商存儲提供者一起儲存的資料

允許使用者使用協力廠商儲存空間提供者儲存檔案的組織，會視這些服務的儲存位置而定，因此請分別檢查其餘服務的資料位置。

- **[** 索引標籤]：索引標籤可讓使用者將應用程式和服務的資訊釘選到頻道。 因此，它會依儲存資料的索引標籤類型而有所不同。 索引標籤本身不會儲存任何資料。 例如，[SharePoint] 索引標籤會根據 SharePoint 網站集合的調配位置來儲存資料。 包括來自合作夥伴之資訊的索引標籤會直接將資料儲存在合作夥伴所使用的系統中，而且只會呈現它的觀點。
- **其他合作夥伴應用程式**： Microsoft 不會針對您在團隊體驗中所使用的合作夥伴提供 app 與服務的任何資料派駐支援。 直接查看這些解決方案中的資訊，以瞭解其資料的儲存位置。

## <a name="see-also"></a>另請參閱

- [Microsoft 團隊會啟動阿拉伯聯合大公國資料派駐](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-United-Arab-Emirates-Data-Residency/ba-p/980330)

- [Microsoft 團隊啟動南亞韓文資料派駐服務](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Korea-Data-Residency/ba-p/789171)

- [Microsoft 團隊啟動南亞非洲資料派駐服務](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Africa-Data-Residency/ba-p/776611)

- [Microsoft 團隊會啟動法國資料派駐服務](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-France-Data-Residency/ba-p/364466)

- [Microsoft 團隊會啟動印度資料派駐服務，即將推出其他 geos](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-India-Data-Residency-other-geos-coming/ba-p/154083)

- [Microsoft 團隊會啟動澳大利亞和日本資料派駐服務](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Australia-and-Japan-Data-Residency/ba-p/237827)

- [Microsoft 團隊隨即推出加拿大的加拿大資料派駐、澳大利亞和日本](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Canada-Data-Residency-Australia-and/ba-p/227178)
