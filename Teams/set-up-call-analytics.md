---
title: 設定通話分析Microsoft Teams
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
description: 設定每個使用者的通話分析，以找出和疑難排解Microsoft Teams品質問題。
ms.openlocfilehash: 209fcad851f5ba7b0183a9988372e249f99cc4fd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117131"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a>設定通話分析Microsoft Teams

做為Microsoft Teams系統管理員，您可以使用每個使用者的通話分析來疑難排解個別Teams通話品質與連接 **問題**。 若要充分利用通話分析，請設定下列專案：
  
- 指派特殊支援角色給人員 ，例如技術支援人員，讓他們查看使用者的通話分析。 這些支援角色無法存取系統管理中心的其他Teams角色。 
    
- 上傳 .tsv 或 .csv資料檔案，將建築物、網站和租使用者資訊新.csv分析。
    
當您準備好開始使用每個使用者的通話分析時，請閱讀使用每個使用者通話分析來疑難排解 [通話品質不佳的問題](use-call-analytics-to-troubleshoot-poor-call-quality.md)。
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a>給予支援和支援人員的許可權

作為系統管理員Teams，您可以完全存取所有使用者的通話分析資訊。 我們已建立一些Azure Active Directory角色，您可以將這些角色指派給支援人員及技術支援人員，這樣他們就可以存取每個使用者的通話分析 (，而不需要存取 Teams 系統管理中心) 。 將Teams **通訊支援專家** 角色指派給使用者，這些使用者應能有限地查看第 1 層支援 (使用者) 。 指派Teams **通訊支援工程師** 角色給需要完全存取每使用者通話分析的使用者， (第 2 層支援) 。 兩個角色都不得存取系統管理Teams中心。

若要瞭解每個角色的作用，請參閱每個角色Teams[角色的作用](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)？

若要進一Teams系統管理員角色，請參閱使用 Teams[系統管理員角色來管理Teams。](using-admin-roles.md) 若要瞭解如何在 Azure Active Directory 中指派系統管理員角色，請參閱在 Azure Active Directory[中查看Azure Active Directory。](/Azure/active-directory/users-groups-roles/directory-manage-roles-portal)

若要瞭解如何在 Azure Active Directory 中指派系統管理角色，請參閱在 Azure Active Directory[中查看和指派Azure Active Directory。](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>Upload .tsv 或 .csv檔案來新增建築物、網站和租使用者資訊

您可以上傳檔案或 .tsv 檔案，將建築物、網站和租使用者資訊新增到每個使用者的通話分析.csv。 有了這些資訊，通話分析就可以將 IP 位址與實體位置進行比對。 系統管理員和技術支援人員可以使用這項資訊，協助發現通話問題的趨勢。 例如，為什麼同一棟大樓的使用者有類似的通話品質問題？ 

如果您是系統管理員或Teams商務用 Skype，您可以使用現有的租使用者和建立資料檔案，從 Teams 或 商務用 Skype 通話品質儀表板 (CQD) 。 首先，您從 CQD 下載檔案，然後上傳檔案以呼叫分析。 

- 若要下載現有的資料檔案，請前往系統管理中心Microsoft Teams  >  **通話品質儀表板**  >  **Upload 。** 在 [ **我的上傳清單上** ， **按一下** 您想要的檔案旁的下載。 

- 若要上傳新檔案，請Microsoft Teams系統管理中心位置，然後選取 Upload或  >  ******取代位置資料**。 
  
如果您要從頭開始建立 .tsv 或 .csv檔案，請參閱Upload[及建築物資料](CQD-upload-tenant-building-data.md)。
  
## <a name="related-topics"></a>相關主題

[使用每個使用者的通話分析來疑難排解通話品質不佳的問題](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Teams 疑難排解](/MicrosoftTeams/troubleshoot/teams)