---
title: '[加入檢查清單]-啟用 Microsoft 365 或 Office 365 服務'
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 當您設定 Microsoft 365 或團隊的 Office 365 時，請遵循此檢查清單中的核心、執行任務和活動。
localization_priority: Normal
f1.keywords:
- NOCSH
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2439a2fd23566c93fb60772112da098cff315760
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/09/2020
ms.locfileid: "44665165"
---
# <a name="enable-microsoft-365-or-office-365"></a>啟用 Microsoft 365 或 Office 365
 
| 否 | 活動或任務| 描述| 完畢? | 其他資訊|
|----|-----------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | 建立 Microsoft 365 或 Office 365 組織| 您必須先設定 Microsoft 365 或 Office 365 組織，您的組織才能享受團隊帶來的好處。 如果您沒有 Microsoft 365 或 Office 365 組織，請參閱 [**其他資訊**] 欄中的指導方針。 | | [設定 Microsoft 365 或 Office 365 for business](https://support.office.com/article/Set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa) <br/><br/>[如果您需要其他協助，可使用 microsoft 365 或 Office 365 小組的 Microsoft FastTrack 協助](https://fasttrack.microsoft.com/office) |
| 2  | 購買 Microsoft 365 或 Office 365 授權 | 根據您在團隊構想階段所做的工作結果，與您的購買群組共同作業，以確保貴組織已購買必要的授權 Sku 或附加元件服務，且已準備好將其指派給租使用者。 | | [Microsoft 團隊服務描述](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description) <br/><br/>[購買適用于您 Microsoft 365 或 Office 365 for Business 訂閱的授權](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1) |
| 3  | 將 Microsoft 365 或 Office 365 授權指派給曆 | 通常，您或您的授權系統管理員會收到來自 Microsoft 授權的連結，以將您的授權新增至您的 Microsoft 365 或 Office 365 組織。 <br/><br/>視您用來購買授權的頻道而定，您可能需要造訪 [**其他資訊**] 欄中所列的其中一個指南。 | | [新增授權至支付給使用產品金鑰的訂閱](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53) <br/><br/>[透過大量授權服務中心中心新增授權至購買的訂閱](https://support.office.com/article/Add-licenses-to-a-subscription-purchased-through-the-Volume-Licensing-Service-Center-82ba88fa-ebdf-4d44-a7b3-cea82b25d71a) |
| 4  | 選用：啟用通訊點數 | [通訊點數] 是您用來提供貴組織的會議橋接器電話號碼免費存取的選擇性功能，或是讓會議召集人能夠撥出給國際會議參與者。 <br/><br/>除了標準的音訊會議每個使用者授權之外，大量和授權組織也可以選擇要啟用音訊會議功能的每分鐘付費優惠。 <br/><br/>決定貴組織是否需要通訊點數，如果是的話，請將通訊點數附加元件授權新增至您的租使用者，以啟用它。 | | [什麼是通訊點數？](what-are-communications-credits.md) <br/><br/>[設定貴組織的通訊點數](set-up-communications-credits-for-your-organization.md) <br/><br/>[音訊會議按分鐘計費](audio-conferencing-pay-per-minute.md) |
| 500  | 確認已提供 Microsoft 365 或 Office 365 組織的授權 | 移至 Microsoft 365 系統管理中心，確認它顯示您在 Microsoft 365 或 Office 365 組織中預期的授權 Sku 和數量。 <br/><br/>在**其他資訊**中使用參照來遍歷此程式。 | | [我擁有哪些 Microsoft 365 或 Office 365 商務版訂閱？](https://support.office.com/article/What-Office-365-for-business-subscription-do-I-have-092252f8-08df-4cdb-a8d2-b8653caa29a1) |
| 6  | 設定您的環境以進行身分識別。 | 使用者可以直接在 Microsoft 365 或 Office 365 中建立（在線上部署模型中），或從內部部署 Active Directory 同步處理至您的 Microsoft 365 或 Office 365 組織。 <br/><br/>判斷您是否應該使用雲端身分識別、同步身分識別或同盟身分識別。 判斷正確的身分識別類型超出此檢查清單的範圍，不過，您可以在 [**其他資訊**] 欄中找到這些選項之相關資訊的連結。 <br/><br/>**注意：** 如果您使用的是同步或同盟身分識別，請確定內部部署使用者主體名稱（Upn）與 Microsoft 365 或 Office 365 Upn 相符，且所有必要屬性都已設定為與 Azure AD Connect 同步處理。 針對團隊所需的屬性，請使用商務用 Skype Online 的屬性清單。 | | [瞭解 Microsoft 365 或 Office 365 身分識別與 Azure Active Directory](https://support.office.com/article/Understanding-Office-365-identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9) <br/><br/>[準備透過目錄同步處理將使用者預配至 Microsoft 365 或 Office 365](https://support.office.com/article/Prepare-to-provision-users-through-directory-synchronization-to-Office-365-01920974-9e6f-4331-a370-13aea4e82b3e) <br/><br/>[Azure AD Connect 同步處理：屬性已同步處理到 Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-attributes-synchronized) |
| utf-7  | 確認租使用者管理員 | 與您的安全小組合作，開發 Microsoft 365 或 Office 365 管理模型。 <br/><br/>請務必識別並記錄所有租使用者與服務管理員。 | | [關於 Microsoft 365 或 Office 365 系統管理員角色](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d) |
| 型  | 針對您的租使用者實施管理角色 | 確認您的管理模型符合貴組織的需求，並將 Microsoft 365 或 Office 365 系統管理員角色指派給您的系統管理員。 | | [在 Microsoft 365 或 Office 365 for business 中指派管理員角色](https://support.office.com/article/Assign-admin-roles-in-Office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) |
| 9  | 登入通話品質儀表板（CQD）上傳您的建築物資訊。 | 每個團隊部署都應該利用 CQD，深入瞭解使用團隊之所有通話的品質與可靠性。 <br><br>使用 [**其他資訊**] 欄中所列的 CQD 指南，可充分發揮此工具的益處。 | | [規劃服務管理和品質](https://docs.microsoft.com/MicrosoftTeams/prepare-network) <br/><br/>[品質體驗回顧指南](https://aka.ms/qerguide) <br/><br/>[優質體驗回顧範本](https://aka.ms/qertemplates) <br/><br/>[開啟並使用 Microsoft 團隊及商務用 Skype Online 的通話品質儀表板](https://support.office.com/article/Turning-on-and-using-Call-Quality-Dashboard-for-Microsoft-Teams-and-Skype-for-Business-Online-553fa13c-92d2-4d5c-a3d5-41a073cb047c)<br><br>[上傳建築物資訊](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard?#upload-building-information) |
| 第  | 確認已處理建築物資訊，且通話品質儀表板（CQD）對於您的租使用者可執行。 | | | [通話品質儀表板](https://cqd.lync.com) |
