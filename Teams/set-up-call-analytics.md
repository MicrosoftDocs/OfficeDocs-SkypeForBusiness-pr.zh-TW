---
title: 設定 Microsoft 團隊的呼叫分析
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, vkorlep
ms.topic: article
ms.assetid: fbf7247a-84ae-46cc-9204-2c45b1c734cd
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
description: 設定每個使用者的呼叫分析，以找出並解決 Microsoft 團隊通話品質問題。
ms.openlocfilehash: f1ea46f275dfbbe5ea7f6cd40d8c06fba2b5e00f
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581104"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a>設定 Microsoft 團隊的呼叫分析

做為 Microsoft 團隊管理員，您可以使用每個使用者的呼叫分析來疑難排解小組針對**個別使用者**呼叫品質與連線問題。 若要充分利用呼叫分析，請設定下列專案：
  
- 將特殊支援角色指派給人員（例如支援者的 agent），讓他們能夠查看使用者的呼叫分析。 這些支援角色無法存取其他團隊系統管理中心。 
    
- 透過上傳 tsv 或 .csv 資料檔，將建築物、網站和租使用者資訊新增至每個使用者呼叫分析。
    
當您準備好要開始使用每個使用者的呼叫分析時，請閱讀[使用每個使用者的呼叫分析，以解決通話品質不佳的問題](use-call-analytics-to-troubleshoot-poor-call-quality.md)。
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a>授與支援人員及技術支援人員的許可權

就團隊管理員而言，您擁有所有使用者的呼叫分析資訊的完整存取權。 我們已建立一些專用的 Azure Active Directory 角色，您可以將它指派給支援人員和支援人員的代理，讓他們也能存取每位使用者的呼叫分析 (，而不需存取團隊系統管理員中心的其他部分) 。 將**團隊通訊支援專家**角色指派給應該擁有有限的每使用者呼叫分析視圖的使用者， (第1層支援) 。 指派**團隊通訊支援工程師**角色給需要對每位使用者呼叫分析進行完整存取的使用者， (第2層支援) 。 兩個角色都無法存取其他團隊系統管理中心。

若要瞭解這些角色的作用，請閱讀[每個團隊支援角色的功能是什麼](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)？

如需有關團隊管理員角色的詳細資訊，請參閱[使用團隊管理員角色管理團隊](using-admin-roles.md)。 若要瞭解如何在 Azure Active Directory 中指派系統管理員角色，請參閱[在 Azure Active directory 中查看和指派角色](https://docs.microsoft.com/Azure/active-directory/users-groups-roles/directory-manage-roles-portal)。

若要瞭解如何在 Azure Active Directory 中指派系統管理角色，請參閱[在 Azure Active directory 中查看和指派角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)。

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>上傳. tsv 或 .csv 檔案，以新增建築物、網站和租使用者資訊

您可以透過上傳 .csv 或 tsv 檔案，將建築物、網站和租使用者資訊新增至每個使用者呼叫分析。 在所有這些資訊的情況下，呼叫分析可以將 IP 位址對應至物理位置。 系統管理員和支援人員都可以使用這項資訊來協助找出通話問題的趨勢。 例如，為什麼同一個建築物中的使用者有類似的通話品質問題？ 

如果您是團隊或商務用 Skype 系統管理員，您可以使用現有的租使用者，並從 [小組] 或 [商務用 Skype 通話品質] 儀表板中建立資料檔， (CQD) ]。 首先，您要從 CQD 下載檔案，然後將檔案上傳到 [呼叫分析]。 

- 若要下載現有的資料檔，請移至**Microsoft 團隊系統管理中心**的  >  **通話品質儀表板**  >  **[立即上傳**]。 在 [**我**的上傳] 清單中，按一下您想要的檔案旁的 [**下載**]。 

- 若要上傳新檔案，請移至**Microsoft 團隊系統管理中心**  >  **位置**，然後選取 **[上傳位置資料**] 或 [**取代位置資料**]。
  
如果您要從頭開始建立 tsv 或 .csv 檔案，請參閱[上傳租使用者及組建資料](CQD-upload-tenant-building-data.md)。
  
## <a name="related-topics"></a>相關主題

[使用每位使用者通話分析來排查不佳的通話品質問題](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Teams 疑難排解](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
