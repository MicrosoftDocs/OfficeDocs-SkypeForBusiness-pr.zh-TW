---
title: 管理組織的 [班次] 應用程式
author: serdarsoysal
ms.author: serdars
ms.reviewer: lisawu,gumariam
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: 瞭解如何在組織中為前線員工Teams中設定及管理 Shifts 應用程式。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 87389dfaba68de8cfe02f3291e03d593bb9de75b
ms.sourcegitcommit: 3a8bec0445cee5cd776fb1991f093a0ec4351852
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/28/2021
ms.locfileid: "60605829"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>在 Microsoft Teams 中管理貴組織的 [班次] 應用程式

> [!IMPORTANT]
> 自 2020 年 6 月 30 起，已終止對 Microsoft StaffHub 的支援。 我們正在將 StaffHub 功能建入 Microsoft Teams。 今天，Teams 包含用於排程管理的班次應用程式，並且會陸續推出其他功能。 所有使用者自 2020 年 6 月 30 日起皆無法再使用 StaffHub。 任何嘗試開啟 StaffHub 的人，都會看到一則訊息，指示他們下載 Teams。 如需深入了解，請參閱[已終止對 Microsoft StaffHub 的支援](microsoft-staffhub-to-be-retired.md)。  

## <a name="overview-of-shifts"></a>班次概觀

應用程式中的 Shifts 應用程式Microsoft Teams前線員工保持連接與同步。這是專為團隊快速且有效的時間管理與通訊所打造的行動電話。 輪班讓前線員工及其主管使用行動裝置管理排程並保持聯繫。

- 主管建立、更新及管理團隊的排班表。 主管也可以傳送訊息給單一個人 (「地板上有打翻的液體」) 或整個團隊 (「區域總經理將於 20 分鐘後抵達」)。 主管還可以傳送原則文件、新訊佈告欄或影片。
- 員工可查看預排的班次、查看當天還有誰已排班、要求調班或調班，以及要求請假。

請注意，Shifts 目前不支援來賓。 這表示在 Teams 中開啟來賓存取時，團隊中的來賓無法新增或使用班次排程。 

> [!Note]
> 如需有關不同平台上班次功能的詳細資訊，請參閱[依平台的 Teams 功能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。

## <a name="availability-of-shifts"></a>班次的可用性

班次可在可用 Teams 的所有企業 SKUS 中使用。

## <a name="location-of-shifts-data"></a>班次資料的位置

班次資料目前儲存在位於北美洲、西歐和亞太地區資料中心的 Azure 中。 如需有關資料儲存位置的詳細資訊，請參閱[我的資料在哪裡](http://o365datacentermap.azurewebsites.net/)？

## <a name="set-up-shifts"></a>設定班次

### <a name="enable-or-disable-shifts-in-your-organization"></a>啟用或停用組織中的 [班次]

您的組織中的所有 Teams 使用者預設會啟用 [班次]。 您可以在 Microsoft Teams 系統管理中心的[管理應用程式](../../manage-apps.md)頁面上關閉或開啟組織層級的應用程式。

1. 在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 **Teams 應用程式** > **管理應用程式**。
2. 在應用程式清單中，執行下列其中一項動作：

    - 若要關閉貴組織的 [班次]，請搜尋 [班次] 應用程式，加以選取，然後選取 **封鎖**。
    - 若要開啟貴組織的 [班次]，請搜尋 [班次] 應用程式，加以選取，然後選取 **允許**。

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a>啟用或停用組織中特定使用者的 [班次]

若要允許或封鎖貴組織的特定使用者使用 Shifts，請確定貴組織在管理應用程式頁面上已開啟[Shifts。](../../manage-apps.md) 然後建立自訂應用程式權限原則，並將其指派給這些使用者。 若要深入了解，請參閱[管理 Teams 中的應用程式權限原則](../../teams-app-permission-policies.md)。

### <a name="use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams"></a>使用 FirstLineWorker 應用程式設定政策將 Shifts 釘Teams

應用程式設定原則可讓您自訂 Teams，以醒目提示對貴組織中使用者最重要的應用程式。 您在原則中設定的應用程式會釘選到應用程式列&mdash;位於 Teams 桌面版用戶端側邊列，以及位於 Teams 行動版用戶端底部&mdash;，可讓使用者快速且輕鬆地存取。
 
Teams內建的 FirstLineWorker 應用程式設定策略，您可以指派給貴組織的前線工作人員。 根據預設，此原則包含活動、班次、聊天和通話應用程式。

若要查看 FirstLineWorker 政策，在系統管理中心的左側導Microsoft Teams，請前往 Teams **設定**  >  **策略**。

:::image type="content" source="../../media/firstline-worker-app-setup-policy-new.png" alt-text="系統管理中心中 FirstLineWorker 應用程式設定Microsoft Teams的螢幕擷取畫面" lightbox="../../media/firstline-worker-app-setup-policy-new.png":::

#### <a name="assign-the-firstlineworker-app-setup-policy-to-users"></a>指派 FirstLineWorker 應用程式設定策略給使用者

[!INCLUDE [assign-policy](../../includes/assign-policy.md)]

## <a name="search-the-audit-log-for-shifts-events"></a>搜尋班次活動的稽核記錄檔

**(預覽)**

您可以搜尋稽核記錄來查看貴組織的班次活動。  如需深入了解如何搜尋稽核記錄，以及查看稽核記錄中記錄的[班次活動](../../audit-log-events.md#shifts-in-teams-activities)清單，請參閱 [在 Teams 中搜尋活動的稽核記錄](../../audit-log-events.md)。

在您可以搜尋稽核記錄檔之前，您必須先在[安全性與合規性中心](https://protection.office.com)中開啟稽核。 如需深入了解，請參閱[開啟或關閉稽核記錄](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)。 請記住，只有當您開啟稽核時，才能使用稽核資料。

## <a name="related-topics"></a>相關主題

- [第一線員工輪班協助](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [在 Teams 中將原則指派給使用者](../../policy-assignment-overview.md)
