---
title: Microsoft 團隊中的身分識別模型與驗證
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: reference
ms.service: msteams
ms.reviewer: anach
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 瞭解 Microsoft 團隊（例如雲端、同步處理及同盟）中的不同身分識別模型。 此外，您也可以瞭解多重要素驗證。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3e485cc04be2e7bb5220a539d94cdce8e91cb0ec
ms.sourcegitcommit: 2e005b335b1566c99b93fc311498702838466324
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/02/2019
ms.locfileid: "37931621"
---
<a name="identity-models-and-authentication-in-microsoft-teams"></a>Microsoft 團隊中的身分識別模型與驗證
==========================================

Microsoft 團隊支援 Office 365 提供的所有身分識別模型。 支援的身分識別模型包括：

-   **雲端身分識別**：在這個模型中，使用者是在 Office 365 中建立和管理，並儲存在 Azure active directory 中，且密碼是由 Azure active directory 驗證。

-   已同步處理身分**識別**：在這個模型中，使用者身分識別是在內部部署伺服器中管理，帳戶和密碼雜湊會同步處理到雲端。 使用者會在內部部署中輸入相同的密碼，就像在雲端中一樣，而登入密碼是由 Azure Active Directory 驗證。 此模型使用 Microsoft Azure Active Directory Connect 工具。

-   同盟身分**識別**：此模型需要已同步身分識別，且由內部部署身分識別提供者驗證使用者密碼。 在這個模型中，密碼雜湊不需要同步處理到 Azure AD，而且 Active Directory 同盟服務（ADF）或協力廠商身分識別提供者是用來針對內部部署的 Active Directory 驗證使用者。

<a name="configurations"></a>設定
--------------

根據貴組織所要實施及使用的身分識別模型決定，實現需求可能會有所不同。 請參閱下方的 [需求] 資料表，以確保您的部署符合這些先決條件。 如果您已經部署 Office 365，而且已經實現身分識別與驗證方法，您可以略過這些步驟。


|身分識別模型 |部署檢查清單  |其他資訊  |
|---------|---------|---------|
|* All     |<ol type="1"><li>比較 Office 365 方案選項並取得訂閱</li><li>建立 Office 365 租使用者</li><li>將 Office 365 授權指派給租使用者</li><li>設定網域和系統管理員使用者</li><li>繼續使用身分識別模型的特定指示</li></ol>          |<ul style="list-style-type:none"><li>[Office 365 方案選項](https://technet.microsoft.com/library/office-365-plan-options.aspx)</li><li>[比較 Office 365 商務方案](https://go.microsoft.com/fwlink/?linkid=854617)</li><li>[購買商務用 Office 365 訂閱的授權](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1)</li><li>[新增授權至訂閱](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53)</li><li>[設定商務用 Office 365](https://support.office.com/Article/set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa)</li><li>[使用 [設定] 嚮導新增使用者和網域](https://support.office.com/article/Add-users-and-domain-with-the-setup-wizard-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</li><li>注意：如果您需要協助，可使用[Microsoft Office 365 團隊的 Microsoft FastTrack](https://go.microsoft.com/fwlink/?linkid=854618) 。</li></ul>          |
|雲端身分識別     |<ol type="1"><li>使用 Office 365 系統管理入口網站建立使用者</li></ol>           |<ul style="list-style-type:none"><li>[個別或大量將使用者新增至 Office 365](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)</li></ul>         |
|已同步身分識別     |<ol type="1"><li>安裝 Azure AD Connect</li><li>設定目錄同步處理</li><li>使用內部部署的 Active Directory 管理工具建立使用者</li></ol>         |<ul style="list-style-type:none"><li>[設定 Office 365 的目錄同步處理](https://support.office.com/article/Set-up-directory-synchronization-for-Office-365-1b3b5318-6977-42ed-b5c7-96fa74b08846)</li><li>注意：必須同步處理 Office 365 的密碼雜湊，才能執行驗證。</li></ul>         |
|同盟身分識別    |<ol type="1"><li>安裝 Azure AD Connect</li><li>設定目錄同步處理</li><li>安裝和設定聯合身分識別提供者（建議使用 ADFS）</li><li>使用內部部署的 Active Directory 管理工具建立使用者</li></ol>           |<ul style="list-style-type:none"><li>[設定 Office 365 的目錄同步處理](https://support.office.com/article/Set-up-directory-synchronization-for-Office-365-1b3b5318-6977-42ed-b5c7-96fa74b08846)</li><li>[規劃您的 AD FS 部署](https://go.microsoft.com/fwlink/?linkid=854619)</li><li>[檢查清單：部署您的同盟伺服器群](https://go.microsoft.com/fwlink/?linkid=854620)</li><li>[針對 AD FS 設定外部網路存取](https://go.microsoft.com/fwlink/?linkid=854621)</li><li>[在 AD FS 與 Azure AD 之間設定信任關係](https://go.microsoft.com/fwlink/?linkid=854622)</li><li>[使用 ADFS 驗證及管理單一登入](https://go.microsoft.com/fwlink/?linkid=854624)</li><li>[Azure AD 同盟相容性清單](https://go.microsoft.com/fwlink/?linkid=854625)</li><li>注意：密碼雜湊不需要同步處理到 Azure Active Directory。</li></ul>         |

如需其他詳細資料，請參閱[選擇 office 365 的登入模型](https://go.microsoft.com/fwlink/?linkid=854626)及[瞭解 office 365 身分識別和 Azure Active Directory](https://support.office.com/article/Understanding-Office-365-identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9)指南。

<a name="multi-factor-authentication"></a>多重要素驗證
----------------------------

Office 365 方案支援多重要素驗證（MFA），可增加 Office 365 服務的使用者登錄安全性。 透過 MFA for Office 365，使用者正確輸入其密碼之後，就必須確認電話撥、短訊息或代理程式更新。 只有在滿足這個第二個驗證因素之後，使用者才能登入。

任何包含 Microsoft 團隊的 Office 365 方案都支援多重要素驗證。 以下是包含 Microsoft 團隊的 Office 365 訂閱者案將在下文的 [授權] 區段中討論。

當使用者登入 MFA 之後，下次使用者登入時，會看到一則訊息，要求他們設定其第二個驗證因數。 支援的驗證方法如下：


|租使用者類型  |可用的 MFA 第二個因數選項  |筆記  |
|---------|---------|---------|
|**僅限雲端**     |針對 Office 365 的 MFA <ul><li>通話</li><li>文字訊息</li><li>行動代理程式更新</li><li>行動應用程式驗證碼</li></ul>        |[規劃 Office 365 部署的多重要素驗證](https://support.office.com/article/Plan-for-multi-factor-authentication-for-Office-365-Deployments-043807b2-21db-4d5c-b430-c8a6dee0e6ba)         |
|**混合式設定（已同步或聯合身分識別模型）**     |<ul><li>針對 Office 365 的 MFA</li><li>Azure MFA 模組（ADFS 整合）</li><li>物理或虛擬智慧卡（ADFS 整合）</li></ul>         |注意：您可以使用[AZURE AD 身分識別提供者相容性](https://www.microsoft.com/en-us/download/details.aspx?id=56843)檔的其他 MFA 解決方案         |
