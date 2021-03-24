---
title: 上機檢查清單 - 啟用 Microsoft 365 或 Office 365 服務
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 當您設定 Microsoft 365 或 Office 365 for Teams 時，請遵循此檢查清單的核心、工作與活動。
localization_priority: Normal
f1.keywords:
- NOCSH
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 54358269658ec7fc531bc6e18c3b08eab817040d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098019"
---
# <a name="enable-microsoft-365-or-office-365"></a>啟用 Microsoft 365 或 Office 365
 
| 否 | 活動或工作| 說明| 完成？ | 其他資訊|
|----|-----------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | 建立 Microsoft 365 或 Office 365 組織| 您的組織必須先設定 Microsoft 365 或 Office 365 組織，才能享有 Teams 的好處。 如果您沒有 Microsoft 365 或 Office 365 組織，請參閱其他資訊列中 **的** 指南。 | | [設定 Microsoft 365 或商務用 Office 365](https://support.office.com/article/Set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa) <br/><br/>[如果您需要其他協助，Microsoft 365 或 Office 365 小組可提供協助](https://fasttrack.microsoft.com/office) |
| 2  | 購買 Microsoft 365 或 Office 365 授權 | 根據 Teams 構想階段期間的工作成果，請與採購群組合作，確保貴組織已購買必要的授權 SKUs 或附加元件服務，並且準備好要指派給租使用者。 | | [Microsoft Teams 服務描述](/office365/servicedescriptions/teams-service-description) <br/><br/>[購買 Microsoft 365 或商務用 Office 365 訂閱授權](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1) |
| 3  | 將 Microsoft 365 或 Office 365 授權指派給組織 | 一般來說，您或您的授權系統管理員會收到 Microsoft 授權的連結，將授權新增到您的 Microsoft 365 或 Office 365 組織。 <br/><br/>根據您用來購買授權哪個頻道，您可能需要流覽其他資訊列中所列的其中一 **個** 指南。 | | [使用產品金鑰付費的訂閱新增授權](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53) <br/><br/>[在透過大量授權服務中心購買的訂閱中新增授權](https://support.office.com/article/Add-licenses-to-a-subscription-purchased-through-the-Volume-Licensing-Service-Center-82ba88fa-ebdf-4d44-a7b3-cea82b25d71a) |
| 4  | 選擇性：啟用通訊信用額度 | 通訊信用額度是一項選擇性功能，您可以使用此功能為貴組織的會議橋接器電話號碼提供免付費存取權，或讓會議召集人能夠撥出給國際會議參與者。 <br/><br/>除了標準的每個使用者音訊會議授權之外，大量和授權組織也可以選擇每分鐘付費優惠，以啟用音訊會議功能。 <br/><br/>決定貴組織是否需要通訊信用額度，如果是的話，請新增通訊信用額度附加元件授權給租使用者以啟用。 | | [什麼是通訊點數？](what-are-communications-credits.md) <br/><br/>[設定貴組織的通訊點數](set-up-communications-credits-for-your-organization.md) <br/><br/>[音訊會議按分鐘計費](audio-conferencing-pay-per-minute.md) |
| 5  | 確認 Microsoft 365 或 Office 365 組織提供授權 | 請前往 Microsoft 365 系統管理中心，確認中心顯示您 Microsoft 365 或 Office 365 組織中預期授權 SKUs 和數量。 <br/><br/>使用其他資訊 **中的** 參照，以完成此程式。 | | [我擁有哪些 Microsoft 365 或商務用 Office 365 訂閱？](https://support.office.com/article/What-Office-365-for-business-subscription-do-I-have-092252f8-08df-4cdb-a8d2-b8653caa29a1) |
| 6  | 設定您的身分標識環境。 | 使用者可以直接在 Microsoft 365 或 Office 365 (線上部署模型) 中建立，或從內部部署 Active Directory 同步處理至您的 Microsoft 365 或 Office 365 組織。 <br/><br/>決定是否要使用雲端身分身分、同步化身分身分或聯盟身分。 判斷正確的身分識別類型超出此檢查清單的範圍;不過，您可以在其他資訊列中找到這些選項 **相關資訊** 的連結。 <br/><br/>**注意：** 如果您使用的是同步處理或聯合身分認證，請確定內部部署使用者主體名稱 (UPNs) 符合 Microsoft 365 或 Office 365 UPNs，而且已針對與 Azure AD Connect 同步處理的所有所需屬性進行配置。 針對 Teams 所需的屬性，請使用商務用 Skype Online 的屬性清單。 | | [瞭解 Microsoft 365 或 Office 365 身分識別與 Azure Active Directory](https://support.office.com/article/Understanding-Office-365-identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9) <br/><br/>[準備透過目錄同步處理將使用者配置至 Microsoft 365 或 Office 365](https://support.office.com/article/Prepare-to-provision-users-through-directory-synchronization-to-Office-365-01920974-9e6f-4331-a370-13aea4e82b3e) <br/><br/>[Azure AD Connect 同步：同步到 Azure Active Directory 的屬性](/azure/active-directory/connect/active-directory-aadconnectsync-attributes-synchronized) |
| 7  | 確認租使用者系統管理員 | 與安全性小組合作，開發 Microsoft 365 或 Office 365 系統管理模型。 <br/><br/>請務必識別所有租使用者和服務系統管理員並記錄。 | | [關於 Microsoft 365 或 Office 365 系統管理員角色](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d) |
| 8  | 為租使用者執行系統管理角色 | 驗證您的系統管理模型符合貴組織的需求，並將 Microsoft 365 或 Office 365 系統管理員角色指派給系統管理員。 | | [在 Microsoft 365 或商務用 Office 365 中指派系統管理員角色](https://support.office.com/article/Assign-admin-roles-in-Office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) |
| 9  | 請于 CQD 中 (通話品質儀表板) 上傳您的建築物資訊。 | 每個 Teams 部署都應該運用 CQD，深入瞭解所有使用 Teams 的通話品質和可靠性。 <br><br>使用其他資訊列中所列的 CQD **指南，** 以從此工具獲得最大好處。 | | [規劃服務管理和品質](./prepare-network.md) <br/><br/>[品質經驗檢閱指南](./quality-of-experience-review-guide.md) <br/><br/>[品質體驗檢閱範本](https://aka.ms/qertemplates) <br/><br/>[開啟及使用 Microsoft Teams 和商務用 Skype Online 的通話品質儀表板](https://support.office.com/article/Turning-on-and-using-Call-Quality-Dashboard-for-Microsoft-Teams-and-Skype-for-Business-Online-553fa13c-92d2-4d5c-a3d5-41a073cb047c)<br><br>[上傳建築物資訊](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information) |
| 10  | 驗證建築物資訊是否經過處理，且您的租使用者 (通話品質儀表板) 可操作。 | | | [通話品質儀表板](https://cqd.teams.microsoft.com) |