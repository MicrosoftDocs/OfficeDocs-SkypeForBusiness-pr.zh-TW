---
title: 檢查您環境的 Microsoft 團隊準備情況
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 5/11/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dansteve
description: 瞭解檢查您的環境準備好 Microsoft 團隊時要尋找的內容。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7988d286c7f75f880572f42793568eb083929e8e
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573038"
---
<a name="check-your-environments-readiness-for-microsoft-teams"></a>檢查您環境的 Microsoft 團隊準備情況
===========================================

每個組織的轉換到雲端都會有所不同，而且目前的狀態可能會影響團隊的運作方式。

在部署 Microsoft 團隊前，強烈建議您先[部署學校資料同步](https://docs.microsoft.com/schooldatasync/)處理。 學校資料同步處理使用學校的 SIS 名單資料來自動建立 Microsoft 團隊及其他應用程式的類別和群組。

若要在小組中取得最佳的體驗，貴組織必須已部署 Exchange Online 和 SharePoint Online。 您也必須確定您目前的環境已準備好供團隊完成。  如需協助，請參閱下列連結：

-   如果您的組織尚未部署任何 Office 365 工作負荷，請參閱[商務用 Office 365 快速入門。](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)

-   如果您的組織尚未新增或設定 Office 365 的驗證網域，請參閱[驗證您的 office 365 網域](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)。

-   如果您的組織尚未將身分識別與 Azure Active Directory 同步處理，請參閱[Microsoft 團隊中的身分識別模型和驗證](identify-models-authentication.md)。

-   如果您的組織沒有 Exchange Online，請參閱[瞭解 exchange 與 Microsoft 團隊互動的方式](Exchange-Teams-interact.md)。

-   如果您的組織沒有 SharePoint Online，請參閱[瞭解 Sharepoint online 與商務用 OneDrive 與 Microsoft 團隊互動的方式](SharePoint-OneDrive-interact.md)。

- 如果您的組織是教育機構，且您是使用學生資訊系統（SIS），請在部署 Microsoft 團隊之前先[部署學校資料同步](https://docs.microsoft.com/schooldatasync/)處理。

- 如果您的組織有現有的內部部署商務用 Skype 伺服器（或 Lync Server）部署，您必須設定 Azure AD Connect，以將您的內部部署目錄與 Office 365 同步處理。  如需詳細資訊，請參閱[設定團隊與商務用 Skype 的 AZURE AD Connect](https://docs.microsoft.com/en-us/skypeforbusiness/hybrid/configure-azure-ad-connect)。