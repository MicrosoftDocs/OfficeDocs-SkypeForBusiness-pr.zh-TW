---
title: 使用者身分識別模型Microsoft Teams
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.date: 09/25/2020
ms.topic: reference
ms.service: msteams
ms.reviewer: anwara
audience: admin
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: 瞭解雲端和混合式Microsoft Teams不同的身分識別模型。 另請瞭解多重要素驗證。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: cea02bf51c474e9be7aca205aa73fd9558f03ad104e5e1a1bde8f5ddc39e95ff
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54342977"
---
# <a name="identity-models-and-authentication-for-microsoft-teams"></a>使用者身分識別模型Microsoft Teams

Microsoft Teams支援所有與 Microsoft 365 和 Office 365一起可用的身分識別模型，包括：

- **雲端：** 使用者帳戶是在 Microsoft 365 或 Office 365 中建立和管理，Azure Active Directory (Azure AD) 。 使用者登錄認證 (帳戶名稱和密碼) Azure AD 進行驗證。

- **混合** 式：使用者帳戶通常是在內部部署 Active Directory Domain Services (AD DS) 管理。 根據配置，認證驗證可以由 Azure AD、AD DS 或聯盟身分識別提供者執行。 此模型使用從 AD DS 到 Azure AD 的目錄同步處理與 Azure AD 連線。

詳細資訊，請參閱Microsoft 365[模型和 Azure AD。](/microsoft-365/enterprise/about-microsoft-365-identity)

## <a name="configurations"></a>配置

根據貴組織決定使用的身分識別模型和組式，執行步驟可能會有所不同。

如果您尚未部署Microsoft 365或Office 365，請使用此資料表。 

|身分識別模型 |部署檢查清單  |其他資訊  |
|---------|---------|---------|
|* All     |<ol type="1"><li>比較Microsoft 365 Office 365方案選項，並取得訂閱和租使用者。</li><li>為租Microsoft 365建立Office 365或組織。</li><li>購買Microsoft 365或Office 365租使用者授權</li><li>設定網域和系統管理員使用者帳戶。</li></ol>  |<ul><li>[Office 365方案選項](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)</li><li>[比較Microsoft 365方案](https://go.microsoft.com/fwlink/?linkid=854617)</li><li>[購買或移除訂閱授權](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1)</li><li>[在訂閱中新增授權](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53)</li><li>[設定Microsoft 365商務用](https://support.office.com/Article/set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa)</li><li>[使用設定精靈新增網域](https://support.office.com/article/Add-users-and-domain-with-the-setup-wizard-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</li></ul><br>[Microsoft FastTrack](https://www.microsoft.com/fasttrack/microsoft-365)可協助您。  |
|雲端身分識別     |<ul><li>使用帳戶建立Microsoft 365 系統管理中心</li></ul> |<ul style="list-style-type:none"><li>[新增使用者並指派授權](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)</li></ul> |
|混合式身分識別     |<ol type="1"><li>安裝 Azure AD 連線。</li><li>設定目錄同步處理。</li><li>使用 AD DS 工具管理使用者和群組。</li></ol> |<ul style="list-style-type:none"><li>[設定目錄同步處理](/microsoft-365/enterprise/set-up-directory-synchronization)</li></ul> |
|使用聯合驗證的混合身分識別    |<ol type="1"><li>安裝並設定聯合身分識別提供者 ，例如 AD FS。</li><li>安裝 Azure AD 連線並設定目錄同步處理和聯合驗證。</li><li>使用 AD DS 工具管理使用者和群組。</li></ol> |<ul><li>[規劃您的 AD FS 部署](/previous-versions/azure/azure-services/dn151324(v=azure.100))</li><li>[檢查清單：部署您的同盟伺服器伺服器組](/previous-versions/azure/azure-services/dn528856(v=azure.100))</li><li>[設定 AD FS 的外網存取](/previous-versions/azure/azure-services/dn528859(v=azure.100))</li><li>[設定 AD FS 與 Azure AD 之間的信任](/previous-versions/azure/azure-services/jj205461(v=azure.100))</li><li>[使用 ADFS 驗證及管理單一登入](/previous-versions/azure/azure-services/jj151809(v=azure.100))</li><li>[設定目錄同步處理](/microsoft-365/enterprise/set-up-directory-synchronization)</li></ul> |
||||

## <a name="multi-factor-authentication"></a>多重要素驗證

密碼是最常見的電腦或線上服務驗證方法，但也是最容易受到攻擊的。 使用者可以選擇簡易密碼，並針對不同的電腦和服務使用多個登錄使用相同的密碼。 

若要為登錄提供額外的安全性等級，請使用多重要素驗證 (MFA) ，這需要密碼和其他驗證方法，例如：

- 一則要使用者輸入驗證碼的訊息。
- 通話。
- Microsoft Authenticator智慧型手機應用程式。
- 混合身分識別與聯合驗證提供的其他方法。

MFA 支援任何包含Microsoft 365或Office 365方案Microsoft Teams。 強烈建議您至少為指派系統管理員角色的帳戶使用 MFA，例如Teams管理員。 [](/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide)

您也應該將 MFA 推出給使用者。 一旦使用者註冊 MFA，下次他們登錄時，就會看到一則訊息，要求他們設定其他驗證方法。 

詳細資訊，請參閱[多重要素驗證的 Microsoft 365。](/microsoft-365/admin/security-and-compliance/multi-factor-authentication-microsoft-365)