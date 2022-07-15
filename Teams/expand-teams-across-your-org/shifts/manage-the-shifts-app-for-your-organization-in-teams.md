---
title: 管理組織的 [班次] 應用程式
author: LanaChin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
description: 瞭解如何在 Teams 中為組織中的一線員工設定和管理 Shifts 應用程式。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
- microsoftcloud-retail
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e97e90a3a6e97bd2637d63cf3ee0d0bceb57dc15
ms.sourcegitcommit: c4ec82b7d8a820362b6b0276470b0dea95a628df
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2022
ms.locfileid: "66819408"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>在 Microsoft Teams 中管理貴組織的 [班次] 應用程式

## <a name="overview-of-shifts"></a>班次概觀

Microsoft Teams 中的 Shifts 應用程式可讓第一線工作人員保持聯繫並保持同步。這是第一次建置行動裝置，可為團隊提供快速且有效的時間管理和通訊。 班次可讓第一線工作人員及其主管使用行動裝置來管理排程並保持聯繫。

- 主管建立、更新及管理團隊的排班表。 主管也可以傳送訊息給單一個人 (「地板上有打翻的液體」) 或整個團隊 (「區域總經理將於 20 分鐘後抵達」)。 主管還可以傳送原則文件、新訊佈告欄或影片。
- 員工可查看預排的班次、查看當天還有誰已排班、要求調班或調班，以及要求請假。

請務必瞭解 Shifts 目前不支援來賓。 這表示在 Teams 中開啟來賓存取時，團隊中的來賓無法新增或使用班次排程。

> [!Note]
> 如需有關不同平台上班次功能的詳細資訊，請參閱[依平台的 Teams 功能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。

## <a name="availability-of-shifts"></a>班次的可用性

班次可在可用 Teams 的所有企業 SKUS 中使用。

> [!NOTE]
> 在政府社群雲端 (GCC) 環境中可以使用 Shifts，但在 GCC High 或 DoD 環境中則不提供。

## <a name="location-of-shifts-data"></a>班次資料的位置

Shifts 資料目前儲存在 Azure 的資料中心，位於亞太地區 (APAC) 、歐盟 (歐盟) ，以及北美洲。 如需有關資料儲存位置的詳細資訊，請參閱[我的資料在哪裡](http://o365datacentermap.azurewebsites.net/)？

若要深入瞭解班次資料，包括儲存空間、保留、擷取和 Shifts 資料加密，請參閱 [Shifts 資料常見問題](shifts-data-faq.md)。

## <a name="set-up-shifts"></a>設定班次

### <a name="enable-or-disable-shifts-in-your-organization"></a>啟用或停用組織中的 [班次]

您的組織中的所有 Teams 使用者預設會啟用 [班次]。 您可以在 Microsoft Teams 系統管理中心的[管理應用程式](../../manage-apps.md)頁面上關閉或開啟組織層級的應用程式。

1. 在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 **Teams 應用程式** > **管理應用程式**。
2. 在應用程式清單中，搜尋 Shifts 應用程式，選取它，然後將 **[狀態]** 切換為 [ **已封鎖** ] 或 [ **允許]**。

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a>啟用或停用組織中特定使用者的 [班次]

若要允許或封鎖貴組織中的特定使用者使用 Shifts，請確定已在 [ [管理應用程式](../../manage-apps.md) ] 頁面上為貴組織開啟 Shifts。 然後建立自訂應用程式許可權原則，並將它指派給這些使用者。 若要深入了解，請參閱[管理 Teams 中的應用程式權限原則](../../teams-app-permission-policies.md)。

### <a name="pin-shifts-to-teams"></a>將班次釘選到 Teams

#### <a name="use-the-tailored-frontline-app-experience-to-pin-shifts-and-other-apps-to-teams"></a>使用量身打造的第一線應用程式體驗，將 Shifts 和其他應用程式釘選到 Teams

Teams 中量身打造的第一線應用程式體驗可為擁有 [F 授權](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt)的使用者釘選 Teams 中最相關的應用程式。 釘選的應用程式包括班次、無線對講機、工作和核准。 根據預設，此功能為您的第一線工作人員提供專為其需求量身打造的全新體驗。

應用程式會釘選到應用程式行，也就是 Teams 桌面用戶端側邊和 Teams 行動用戶端底部的列，使用者可以在此快速且輕鬆地存取它們。

若要深入瞭解，包括體驗如何與您所設定的應用程式原則搭配運作，請參閱 [為您的第一線員工量身打造 Teams 應用程式](/microsoft-365/frontline/pin-teams-apps-based-on-license?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)。  

#### <a name="use-an-app-setup-policy-to-pin-shifts-to-teams"></a>使用應用程式設定原則將 Shifts 釘選到 Teams

應用程式設定原則可讓您自訂 Teams，釘選對使用者最重要的應用程式。

您可以新增 Shifts 應用程式來建立 [自訂應用程式設定原則](../../teams-app-setup-policies.md) ，然後 [將原則指派給](../../assign-policies-users-and-groups.md) 使用者。 或者，您也可以使用屬於第一線工作人員和第三線管理員原則套件一部分的應用程式設定原則。

Teams 中 [的原則套](../../manage-policy-packages.md) 件是一組預先定義的原則和原則設定，您可以將這些設定指派給組織中具有類似角色的使用者。 [第一線工作者] 和 [第一線管理員] 原則套件中的原則集包含一個應用程式設定原則，可釘選 Shifts 應用程式和其他支援該角色通訊及共同作業活動的應用程式。

我們建議您使用第一線工作人員和一線管理員原則套件，以簡化、簡化及協助在管理前線員工的原則時提供一致性。

## <a name="search-the-audit-log-for-shifts-events"></a>搜尋班次活動的稽核記錄檔

**(預覽)**

您可以搜尋稽核記錄來查看貴組織的班次活動。  如需深入了解如何搜尋稽核記錄，以及查看稽核記錄中記錄的[班次活動](../../audit-log-events.md#shifts-in-teams-activities)清單，請參閱 [在 Teams 中搜尋活動的稽核記錄](../../audit-log-events.md)。

在您可以搜尋稽核記錄檔之前，您必須先在[安全性與合規性中心](https://protection.office.com)中開啟稽核。 如需深入了解，請參閱[開啟或關閉稽核記錄](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)。 請記住，只有當您開啟稽核時，才能使用稽核資料。

## <a name="related-articles"></a>相關文章

- [Teams 中的 Shifts](/microsoft-365/frontline/shifts-for-teams-landing-page)
- [Shifts 資料常見問題](shifts-data-faq.md)
- [Shifts 連接器](/microsoft-365/frontline/shifts-connectors)
- [第一線員工的輪班說明](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [將原則指派給 Teams 中的使用者](../../policy-assignment-overview.md)
