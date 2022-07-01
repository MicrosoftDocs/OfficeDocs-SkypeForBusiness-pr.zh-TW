---
title: 上線檢查清單 - 啟用 Microsoft 365 或 Office 365 服務
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 當您為 Teams 設定 Microsoft 365 或Office 365時，請遵循此檢查清單中的核心待辦事項工作和活動。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 032da118795cf37d93616892a98dd6bad08ad1ce
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2022
ms.locfileid: "66563741"
---
# <a name="enable-microsoft-365-or-office-365"></a>啟用 Microsoft 365 或 Office 365
 
| 否 | 活動或工作| 描述| 完成？ | 其他資訊|
|----|-----------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | 建立 Microsoft 365 或Office 365組織| 您必須先設定 Microsoft 365 或Office 365組織，貴組織才能享受 Teams 的權益。 如果您沒有 Microsoft 365 或Office 365組織，請參閱其他 **資訊** 欄中的指導方針。 | | [設定 Microsoft 365 或商務用 Office 365](https://support.office.com/article/Set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa) <br/><br/>[如果您需要其他協助，您可以使用 Microsoft 365 或Office 365小組Microsoft FastTrack來協助您](https://fasttrack.microsoft.com/office) |
| 2  | 購買 Microsoft 365 或Office 365授權 | 根據您在 Teams 想像階段期間所完成工作的結果，與您的採購小組合作，以確保貴組織已購買必要的授權 SKU 或附加元件服務，並準備好指派給租使用者。 | | [Microsoft Teams 服務描述](/office365/servicedescriptions/teams-service-description) <br/><br/>[購買 Microsoft 365 或商務用 Office 365 訂閱的授權](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1) |
| 3  | 指派 Microsoft 365 或Office 365授權給組織 | 通常您或您的授權系統管理員會收到 Microsoft 授權的連結，以將您的授權新增至您的 Microsoft 365 或Office 365組織。 <br/><br/>視您用來購買授權的通道而定，您可能需要流覽 [ **其他資訊** ] 欄中列出的其中一個指南。 | | [將授權新增至使用產品金鑰所付費的訂閱](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53) <br/><br/>[將授權新增至透過大量授權服務中心購買的訂閱](https://support.office.com/article/Add-licenses-to-a-subscription-purchased-through-the-Volume-Licensing-Service-Center-82ba88fa-ebdf-4d44-a7b3-cea82b25d71a) |
| 4  | 選用：啟用通訊點數 | 通訊點數是您用來提供貴組織會議橋接器電話號碼免付費存取權的選用功能，或讓會議召集人能夠撥出給國際會議參與者。 <br/><br/>除了標準的每個使用者音訊會議授權，大量和授權組織可以選擇每分鐘付費優惠，以啟用音訊會議功能。 <br/><br/>決定貴組織是否需要通訊點數，如果需要的話，請將 Communications Credits 附加元件授權新增至您的租使用者來啟用。 | | [什麼是通訊點數？](what-are-communications-credits.md) <br/><br/>[設定貴組織的通訊點數](set-up-communications-credits-for-your-organization.md) <br/><br/>[音訊會議按分鐘計費](audio-conferencing-pay-per-minute.md) |
| 5  | 確認 Microsoft 365 或Office 365組織可使用授權 | 移至Microsoft 365 系統管理中心，並確認它顯示您在 Microsoft 365 或Office 365組織中預期的授權 SKU 和數量。 <br/><br/>使用 [ **其他資訊** ] 中的參照完成此程式。 | | [我擁有哪些商務用 Microsoft 365 或 Office 365 訂閱？](https://support.office.com/article/What-Office-365-for-business-subscription-do-I-have-092252f8-08df-4cdb-a8d2-b8653caa29a1) |
| 6  | 為您的環境設定身分識別。 | 使用者可以在 Microsoft 365 或Office 365直接 (線上部署模型中建立，) 或從 內部部署的 Active Directory 同步處理至您的 Microsoft 365 或Office 365組織。 <br/><br/>判斷您是否應該使用雲端身分識別、同步處理身分識別或同盟身分識別。 判斷適當的身分識別類型超出此檢查清單的範圍;不過，您可以在 [ **其他資訊** ] 欄中找到這些選項相關資訊的連結。 <br/><br/>**注意：** 如果您使用的是同步處理或同盟身分識別，請確定內部部署使用者主體名稱 (UPN) 符合 Microsoft 365 或 Office 365 UPN，而且所有必要的屬性都已設定為與 Azure AD Connect 同步處理。 針對 Teams 所需的屬性，請使用 商務用 Skype Online 的屬性清單。 | | [瞭解 Microsoft 365 或Office 365身分識別和 Azure Active Directory](https://support.office.com/article/Understanding-Office-365-identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9) <br/><br/>[準備透過目錄同步處理將使用者布建到 Microsoft 365 或Office 365](https://support.office.com/article/Prepare-to-provision-users-through-directory-synchronization-to-Office-365-01920974-9e6f-4331-a370-13aea4e82b3e) <br/><br/>[Azure AD Connect 同步處理：與 Azure Active Directory 同步處理的屬性](/azure/active-directory/connect/active-directory-aadconnectsync-attributes-synchronized) |
| 7  | 確認租使用者系統管理員 | 與您的安全性小組合作開發 Microsoft 365 或Office 365系統管理模型。 <br/><br/>請務必識別並記錄所有租使用者和服務系統管理員。 | | [關於 Microsoft 365 或Office 365系統管理員角色](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d) |
| 8  | 實作租使用者的系統管理角色 | 驗證您的系統管理模型符合貴組織的需求，並指派 Microsoft 365 或Office 365系統管理員角色給您的系統管理員。 | | [在 Microsoft 365 或商務用 Office 365 中指派系統管理員角色](https://support.office.com/article/Assign-admin-roles-in-Office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) |
| 9  | 登入 [通話品質儀表板] (CQD) 上傳您的建築物資訊。 | 每個 Teams 部署都應該運用 CQD，深入瞭解所有使用 Teams 的通話品質和可靠性。 <br><br>使用 [ **其他資訊** ] 欄中所列的 CQD 指導方針，充分利用此工具。 | | [服務管理和品質規劃](./prepare-network.md) <br/><br/>[品質體驗檢閱指南](./quality-of-experience-review-guide.md) <br/><br/>[品質體驗檢閱範本](https://aka.ms/qertemplates) <br/><br/>[開啟和使用 Microsoft Teams 和 商務用 Skype Online 的通話品質儀表板](https://support.office.com/article/Turning-on-and-using-Call-Quality-Dashboard-for-Microsoft-Teams-and-Skype-for-Business-Online-553fa13c-92d2-4d5c-a3d5-41a073cb047c)<br><br>[上傳建築物資訊](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information) |
| 10  | 驗證已處理建築物資訊，且您的租使用者可使用「通話品質儀表板 (CQD) 。 | | | [通話品質儀表板](https://cqd.teams.microsoft.com) |