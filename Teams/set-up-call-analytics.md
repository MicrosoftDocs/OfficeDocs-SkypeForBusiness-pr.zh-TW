---
title: 設定 Microsoft Teams 的通話分析
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
description: 設定每個使用者的通話分析，以找出 Microsoft Teams 通話品質問題並進行疑難排解。
ms.openlocfilehash: bcfe39ccdd9a1a751b49cdc8d0f433e3707635e3
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789938"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a>設定 Microsoft Teams 的通話分析

身為 Microsoft Teams 系統管理員，您可以使用個別使用者的通話分析來疑難排解 **個別使用者** 的 Teams 通話品質和連線問題。 若要充分利用通話分析，請設定下列專案：
  
- 指派特殊支援角色給使用者，例如技術服務專員，讓他們檢視使用者的通話分析。 這些支援角色無法存取 Teams 系統管理中心的其餘部分。 
    
- 上傳 .tsv 或.csv資料檔，以新增建築物、網站和租使用者資訊至每個使用者的通話分析。
    
當您準備好開始使用個別使用者的通話分析時，請參閱 [使用個別使用者通話分析來疑難排解不佳的通話品質](use-call-analytics-to-troubleshoot-poor-call-quality.md)。
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a>授與許可權給支援人員和技術服務人員

身為 Teams 系統管理員，您可以完整存取所有使用者的通話分析資訊。 我們已建立一些特殊 Azure Active Directory 角色，您可以將這些角色指派給支援人員和技術服務專員，讓他們也可以存取每個使用者的通話分析 (而不需要存取其他 Teams 系統管理中心) 。 將 **Teams 通訊支援專家** 角色指派給每個使用者通話分析的有限檢視 (層級 1 支援) 的使用者。 將 **Teams 通訊支援工程師** 角色指派給需要完整存取每個使用者通話分析 (第 2 層支援) 的使用者。 這兩個角色都無法存取 Teams 系統管理中心的其餘部分。

若要瞭解每個角色的作用，請參閱 [每個 Teams 支援角色的功能](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)為何？

如需 Teams 系統管理員角色的詳細資訊，請參閱 [使用 Teams 系統管理員角色管理 Teams](using-admin-roles.md)。 若要瞭解如何在 Azure Active Directory 中指派系統管理員角色，請參 [閱在 Azure Active Directory 中檢視和指派角色](/Azure/active-directory/users-groups-roles/directory-manage-roles-portal)。

若要瞭解如何在 Azure Active Directory 中指派系統管理角色，請參 [閱在 Azure Active Directory 中檢視及指派角色](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)。

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>上傳 .tsv 或.csv檔案以新增建築物、網站和租使用者資訊

您可以上傳.csv或 .tsv 檔案，將建築物、網站和租使用者資訊新增到每個使用者的通話分析。 使用所有這些資訊，通話分析可以將 IP 位址對應到實體位置。 系統管理員和技術服務專員可以使用此資訊來協助找出通話問題的趨勢。 例如，為什麼同一棟大樓的使用者有類似的通話品質問題？ 

如果您是 Teams 或商務用 Skype管理員，您可以使用現有的租使用者，以及從 Teams 或 商務用 Skype 通話品質儀表板 (CQD) 建立資料檔案。 首先，您是從 CQD 下載檔案，然後上傳檔案來呼叫分析。 

- 若要下載現有的資料檔案，請移至 **Microsoft Teams 系統管理中心**  >  **分析&報告**  >  **立即上傳通話品質儀表板**  >  。**** 在 [ **我的上傳** ] 清單中，按一下所要檔案旁的 [ **下載** ]。 

- 若要上傳新檔案，請參閱 [新增及更新報告標籤](/microsoftteams/learn-more-about-site-upload)。
  
如果您是從頭開始建立 .tsv 或.csv檔案，請參閱 [上傳租使用者和建築物資料](CQD-upload-tenant-building-data.md)。
  
## <a name="related-topics"></a>相關主題

[使用個別使用者的通話分析來疑難排解不佳的通話品質](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Teams 疑難排解](/MicrosoftTeams/troubleshoot/teams)
