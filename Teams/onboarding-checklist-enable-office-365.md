---
title: 上機檢查清單 - 啟用Microsoft 365或Office 365服務
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 當您設定Microsoft 365或Office 365時，請遵循此檢查清單Teams。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 88ddd7de72bbf9f39344776292573cbb85320e3e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58582197"
---
# <a name="enable-microsoft-365-or-office-365"></a>啟用Microsoft 365或Office 365
 
| 否 | 活動或工作| 描述| 完成？ | 其他資訊|
|----|-----------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | 建立組織Microsoft 365或Office 365組織| 貴組織必須先設定組織或Teams，才能享有Microsoft 365或Office 365權益。 如果您沒有組織或組織Microsoft 365，請參閱Office 365資訊 **欄中** 的指引。 | | [設定Microsoft 365或Office 365商務用](https://support.office.com/article/Set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa) <br/><br/>[如果您需要其他協助，FastTrack microsoft Microsoft 365或Office 365小組可提供協助](https://fasttrack.microsoft.com/office) |
| 2  | 購買Microsoft 365或Office 365授權 | 根據在 Teams 構想階段期間所執行的工作結果，請與採購群組合作，確保您的組織已購買必要的授權 SKUS 或附加元件服務，並且準備好要指派給租使用者。 | | [Microsoft Teams服務描述](/office365/servicedescriptions/teams-service-description) <br/><br/>[購買商務用訂閱Microsoft 365或Office 365授權](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1) |
| 3  | 指派Microsoft 365或Office 365授權給組織 | 一般來說，您或您的授權系統管理員會收到 Microsoft 授權的連結，將授權新Microsoft 365組織Office 365組織。 <br/><br/>根據您用來購買授權哪個頻道，您可能需要流覽其他資訊列中所列的其中一 **個** 指南。 | | [使用產品金鑰付費的訂閱新增授權](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53) <br/><br/>[在透過大量授權服務中心購買的訂閱中新增授權](https://support.office.com/article/Add-licenses-to-a-subscription-purchased-through-the-Volume-Licensing-Service-Center-82ba88fa-ebdf-4d44-a7b3-cea82b25d71a) |
| 4  | 選擇性：啟用通訊信用額度 | 通訊信用額度是一項選擇性功能，您可以使用此功能為貴組織的會議橋接器電話號碼提供免付費存取權，或讓會議召集人能夠撥出給國際會議參與者。 <br/><br/>除了標準的每個使用者音訊會議授權之外，大量和授權組織也可以選擇每分鐘付費優惠，以啟用音訊會議功能。 <br/><br/>決定是否貴組織需要通訊信用額度，如果是的話，請新增通訊信用額度附加元件授權給租使用者以啟用。 | | [什麼是通訊點數？](what-are-communications-credits.md) <br/><br/>[設定貴組織的通訊點數](set-up-communications-credits-for-your-organization.md) <br/><br/>[音訊會議按分鐘計費](audio-conferencing-pay-per-minute.md) |
| 5  | 確認適用于組織或Microsoft 365 Office 365授權 | 請前往Microsoft 365 系統管理中心並確認它顯示授權 SKUs 和您預期在組織或組織中Microsoft 365 Office 365數量。 <br/><br/>使用其他資訊 **中的** 參照，以完成此程式。 | | [我Microsoft 365商務Office 365訂閱的訂閱或訂閱？](https://support.office.com/article/What-Office-365-for-business-subscription-do-I-have-092252f8-08df-4cdb-a8d2-b8653caa29a1) |
| 6  | 設定您的身分資訊環境。 | 使用者可以直接在 Microsoft 365 或 Office 365 (中建立) 或從內部部署 Active Directory 同步處理至您的 Microsoft 365 或 Office 365 組織。 <br/><br/>決定是否要使用雲端身分身分、同步化身分身分或聯盟身分。 判斷正確的身分識別類型超出此檢查清單的範圍;不過，您可以在其他資訊列中找到這些選項 **相關資訊** 的連結。 <br/><br/>**注意：** 如果您使用的是同步處理或聯合身分標識，請確定內部部署使用者主體名稱 (UPNs) 符合 Microsoft 365 或 Office 365 UPNs，而且已針對與 Azure AD 連線 同步處理的所有所需屬性進行配置。 針對您所需的屬性，請使用 Teams Online 的屬性商務用 Skype清單。 | | [瞭解Microsoft 365或Office 365身分識別Azure Active Directory](https://support.office.com/article/Understanding-Office-365-identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9) <br/><br/>[準備透過目錄同步處理將使用者Microsoft 365或Office 365](https://support.office.com/article/Prepare-to-provision-users-through-directory-synchronization-to-Office-365-01920974-9e6f-4331-a370-13aea4e82b3e) <br/><br/>[Azure AD 連線同步：同步到 Azure Active Directory](/azure/active-directory/connect/active-directory-aadconnectsync-attributes-synchronized) |
| 7  | 確認租使用者系統管理員 | 請與安全小組合作，開發管理Microsoft 365或Office 365模式。 <br/><br/>請務必識別所有租使用者和服務系統管理員並記錄。 | | [關於Microsoft 365或Office 365系統管理員角色](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d) |
| 8  | 為租使用者執行系統管理角色 | 驗證您的系統管理模型是否符合貴組織的需求，並將Microsoft 365或Office 365系統管理員角色指派給系統管理員。 | | [在商務Microsoft 365或Office 365指派系統管理員角色](https://support.office.com/article/Assign-admin-roles-in-Office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) |
| 9  | 請登錄 CQD (品質儀表板) 上傳您的建築物資訊。 | 每個Teams部署都應該運用 CQD，以深入瞭解所有使用 Teams。 <br><br>使用其他資訊列中所列的 CQD **指南，** 以從此工具獲得最大好處。 | | [規劃服務管理和品質](./prepare-network.md) <br/><br/>[品質經驗檢閱指南](./quality-of-experience-review-guide.md) <br/><br/>[品質體驗檢閱範本](https://aka.ms/qertemplates) <br/><br/>[開啟及使用適用于線上Microsoft Teams商務用 Skype儀表板](https://support.office.com/article/Turning-on-and-using-Call-Quality-Dashboard-for-Microsoft-Teams-and-Skype-for-Business-Online-553fa13c-92d2-4d5c-a3d5-41a073cb047c)<br><br>[Upload資訊](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information) |
| 10  | 驗證建築物資訊已處理完畢，且您的租使用者 (CQD) 通話品質儀表板。 | | | [通話品質儀表板](https://cqd.teams.microsoft.com) |