---
title: '適用於 Teams 系統管理員的病患應用程式 '
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: 了解適用於 Teams 系統管理員的病患應用程式
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 2302f117564e1dd00a6f238ca23a8e36c63ae554
ms.sourcegitcommit: e6e6a2a85ff376f97a3af3548e13d1273fa84a52
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/28/2021
ms.locfileid: "52697840"
---
# <a name="patients-app-overview"></a>病患應用程式概觀

> [!NOTE]
> 自 2020 年 10 月 30 日起，病患應用程式已淘汰並且由 Teams 中的[清單應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)取代。 病患應用程式資料會儲存在支援小組之 Office 365 群組的群組信箱中。 所有與病患應用程式相關聯的資料會保留在此群組中，但是無法再透過使用者介面存取。 使用者可以使用[清單應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)來重新建立他們的清單。
>
>使用清單，您的醫療保健組織照護小組可以針對各種案例建立病患清單，範圍從會診和跨學科小組會議到一般病患監視。 請查看清單中的病患範本以開始使用。 若要深入了解如何在組織中管理清單應用程式，請參閱[管理清單應用程式](../../manage-lists-app.md)。

病患應用程式是 Microsoft Teams 市集應用程式，可供所有 Teams 使用者使用。 此應用程式可讓臨床工作者 (例如護士、醫生、社會工作者) 所組成的病患健康小組，針對各種案例 (從會診和跨學科小組會議到一般病患監視) 來策劃和檢閱病患清單。

應用程式有兩種模式：

- 透過 FHIR 連線到 EMR 的 EMR 連線模式。 EMR 連線模式應用程式會保持為私人預覽，而有興趣的客戶或系統管理員可以在 [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) 留下包含其 Microsoft 365 組織相關資訊的電子郵件給 Microsoft，以要求存取該應用程式。
- 讓健康小組手動新增/加入病患資訊的手動模式。 應用程式可在 Teams 應用程式市集中供使用者以私人預覽模式下載。 應用程式可以限制為使用 Teams 中[應用程式設定原則](../../teams-app-setup-policies.md)的特定部分使用者。 若要存取應用程式，您的租用戶必須是技術採用方案 (TAP) 的成員。 請於 [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) 傳送電子郵件給我們，以開始要求存取權的程序。

## <a name="usage-example"></a>使用範例

在醫療病房中每個班次的會診期間，臨床醫生會到護理站聚集，與病房中的病患討論進度的最新更新。  他們著重在主要的關鍵計量 (不一定是醫療或在病患醫療記錄上明確顯示)，並且確保病患根據其診斷是往正確的出院方向前進。 為了對這些病患會診，護士會在小組中的病患應用程式設定費用，其中新增所有臨床醫生，並且將病患新增至病患清單。 在會診期間，護士和病患的其他照護人員可以在其行動裝置上存取 Microsoft Teams 和病患應用程式，並更新裝置上的相關病患資訊，然後健康小組中的其他人就可以查看這些更新和筆記，並保持同步。一天兩次，在班次的開始與結束時，他們也會舉行多次跨學科小組會議來查看病患清單，使用病患應用程式讓自己有基本認識，並且在大型顯示器螢幕上使用病患應用程式來分享每個病患的資訊。 通常，某些臨床醫生可能也會從遠端撥入這些 Teams 會議，參與討論。

## <a name="configure-patients-app"></a>設定病患應用程式

請參閱[管理應用程式中的應用程式Microsoft Teams，](../../teams-app-setup-policies.md)為貴組織啟用病患應用程式。

如需使用者如何存取及安裝病患應用程式至他們擁有或管理的小組的詳細資訊，請參閱[開始使用 Microsoft Teams 病患服務](https://support.office.com/article/get-started-with-microsoft-teams-patients-aa7daebe-706a-4a65-8ce9-b9b79233f393)。

<!-- add link out to client doc, doesn't seem to be available yet, Grant is finalizing -->

## <a name="frequently-asked-questions-faq"></a>常見問題集 (FAQ)

**病患應用程式資料儲存在哪裡？**

使用者在病患應用程式中輸入的所有資料，包括欄/欄位結構描述、輸入到清單和清單項目 (即病患) 的實際資料，都會儲存在安全且符合規範的 Exchange Online 基礎結構中。 所有資料都儲存在與小組相關聯的群組信箱中。 此架構可讓病患應用程式輕鬆履行資料落地、政府雲端支援 (未來提供) 以及其他合規性/資訊保護功能，例如電子文件探索支援。 病患應用程式在小組範圍內運作。 您必須為每個小組安裝應用程式執行個體。

<!-- add link to eDiscovery article for the Patients app, Mark Johnson will finalize soon -->

**我可以在哪裡取得病患應用程式？**

如果病患應用程式是由組織的系統管理員為組織啟用，則任何使用者都可以前往 Teams 應用程式市集，並且將病患應用程式新增至他們是其成員的小組。 如需詳細資訊，請參閱[管理 Microsoft Teams 中的應用程式設定原則](../../teams-app-setup-policies.md)。

**我能否在小組中擁有多個病患應用程式執行個體，因為這是我的病房/單位的運作方式？**

目前您只能為指定小組安裝一個病患應用程式執行個體，且只能在一般頻道中安裝。 不過，在應用程式中可以建立多個清單來解決多重頻道或隔離/分離案例。 根據預設，小組的所有成員可以存取一般頻道中的 [病患] 索引標籤。 

**我可以從病患應用程式匯出所有資料嗎？**
目前不行，但是此功能即將推出。 

**由於此應用程式會容納 PHI，是否有稽核來防止未經授權的存取或法規遵循？**

是，有稽核。 Microsoft Teams 使用者在病患應用程式上執行的每一個 UI 動作都會進行稽核，並可在安全性與合規性中心使用。 詳細資料會在[病患應用程式的稽核記錄](patients-audit.md)中說明。

