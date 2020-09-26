---
title: Microsoft 團隊的身分識別模型和驗證
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
description: 瞭解 Microsoft 團隊（例如僅限雲端及混合式）的不同身分識別模型。 此外，您也可以瞭解多重要素驗證。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 40a06ce75c3ae7a4f85eb1c93064ba3d80c13fc0
ms.sourcegitcommit: a28232f16bfefe6414d1f5a54d5f8c8665eb0e23
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277113"
---
# <a name="identity-models-and-authentication-for-microsoft-teams"></a>Microsoft 團隊的身分識別模型和驗證

Microsoft 團隊支援 Microsoft 365 和 Office 365 提供的所有身分識別模型，其中包括：

- **僅限雲端**：使用者帳戶是在 Microsoft 365 或 Office 365 中建立和管理，並儲存在 Azure Active Directory 中 (azure AD) 。 使用者登入認證 (帳戶名稱和密碼) 由 Azure AD 驗證。

- **混合**式：使用者帳戶通常是在內部部署的 Active Directory 網域服務中管理 (AD DS) 目錄林。 根據設定，認證驗證可以由 Azure AD、AD DS 或同盟身分識別提供者來完成。 此模型使用 Azure AD Connect 的目錄同步處理從 AD DS 到 Azure AD。

如需詳細資訊，請參閱 [Microsoft 365 身分識別模型和 AZURE AD](https://docs.microsoft.com/microsoft-365/enterprise/about-microsoft-365-identity)。

## <a name="configurations"></a>設定

根據貴組織所使用的身分識別模型和配置決定，執行步驟可能會有所不同。

如果您尚未部署 Microsoft 365 或 Office 365 及身分識別模型，請使用此表格。 

|身分識別模型 |部署檢查清單  |其他資訊  |
|---------|---------|---------|
|* All     |<ol type="1"><li>比較 Microsoft 365 與 Office 365 方案選項，並取得訂閱與租使用者。</li><li>為您的租使用者建立 Microsoft 365 或 Office 365 組織。</li><li>購買適用于租使用者的 Microsoft 365 或 Office 365 授權</li><li>設定網域和系統管理員使用者帳戶。</li></ol>  |<ul><li>[Office 365 方案選項](https://technet.microsoft.com/library/office-365-plan-options.aspx)</li><li>[比較 Microsoft 365 for business 方案](https://go.microsoft.com/fwlink/?linkid=854617)</li><li>[購買或移除訂閱授權](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1)</li><li>[新增授權至訂閱](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53)</li><li>[設定適用于商務用的 Microsoft 365](https://support.office.com/Article/set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa)</li><li>[使用 [設定] 嚮導新增網域](https://support.office.com/article/Add-users-and-domain-with-the-setup-wizard-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</li></ul><br>[Microsoft FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) 可協助您使用。  |
|雲端身分識別     |<ul><li>使用 Microsoft 365 系統管理中心建立使用者帳戶</li></ul> |<ul style="list-style-type:none"><li>[新增使用者並指派授權](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)</li></ul> |
|混合式身分識別     |<ol type="1"><li>安裝 Azure AD Connect。</li><li>設定目錄同步處理。</li><li>使用 [AD DS 工具] 管理使用者和群組。</li></ol> |<ul style="list-style-type:none"><li>[設定目錄同步處理](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)</li></ul> |
|混合式身分識別與聯合驗證    |<ol type="1"><li>安裝並設定同盟身分識別提供者（例如 AD FS）。</li><li>安裝 Azure AD Connect 並設定目錄同步處理與聯合驗證。</li><li>使用 [AD DS 工具] 管理使用者和群組。</li></ol> |<ul><li>[規劃您的 AD FS 部署](https://go.microsoft.com/fwlink/?linkid=854619)</li><li>[檢查清單：部署您的同盟伺服器群](https://go.microsoft.com/fwlink/?linkid=854620)</li><li>[針對 AD FS 設定外部網路存取](https://go.microsoft.com/fwlink/?linkid=854621)</li><li>[在 AD FS 與 Azure AD 之間設定信任關係](https://go.microsoft.com/fwlink/?linkid=854622)</li><li>[使用 ADFS 驗證及管理單一登入](https://go.microsoft.com/fwlink/?linkid=854624)</li><li>[設定目錄同步處理](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)</li></ul> |
||||

## <a name="multi-factor-authentication"></a>多重要素驗證

密碼是最常見的登入電腦或線上服務驗證方法，但也是最容易受到攻擊的方法。 使用者可以選擇 [輕鬆密碼]，並在不同的電腦和服務上使用相同的密碼。 

若要為登入提供額外的安全性等級，請使用多重要素驗證 (MFA) ，這需要密碼和其他驗證方法，例如：

- 傳送至手機的文字訊息，要求使用者輸入驗證碼。
- 通話。
- Microsoft 驗證器智慧型電話 app。
- 使用混合式身分識別與同盟驗證的其他方法。

任何包含 Microsoft 團隊的 Microsoft 365 或 Office 365 方案都支援 MFA。 強烈建議您至少需要對 [指派系統管理員角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide)的帳戶（例如團隊服務管理員）進行 MFA。

您也應該將 [MFA] 向您的使用者推出。 當使用者登入 MFA 之後，下次登入時，他們會看到一則訊息，要求他們設定其額外的驗證方法。 

如需詳細資訊，請參閱 [Microsoft 365 的多重要素驗證](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/multi-factor-authentication-microsoft-365)。
