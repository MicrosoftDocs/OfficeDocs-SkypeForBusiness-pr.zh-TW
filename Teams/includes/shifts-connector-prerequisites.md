---
author: LanaChin
ms.author: v-lanachin
ms.date: 03/31/2022
ms.topic: include
audience: admin
ms.service: msteams
ms.openlocfilehash: ab375a876eb62e5f41e5dd7cda3743d4010b95ff
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/31/2022
ms.locfileid: "64593644"
---
在您開始使用之前，請確定您具有下列先決條件：

- 藍色 Yonder WFM 版本 2020.3、2021.1 或 2021.2。

    > [!NOTE]
    > 如果您有 Blue Yonder WFM 2020.3 或 2021.1，請適用 2020.3.0.4 或 2021.1.0.3 修補程式。 此修補程式可修正使用者在 Shifts 中收到永久錯誤訊息的問題。 它也修正了使用者無法更新 Shifts 中的可用性的問題。

- 您的 Blue Yonder WFM 服務帳戶名稱和密碼和服務 URL：

    - 聯合驗證 URL
    - Cookie 驗證 URL
    - 員工自助 URL
    - 零售 Web API URL
    - 網站管理員 API URL
    - 系統管理 API URL

    如果您沒有這項資訊，請聯絡 Blue Yonder 支援人員。 帳戶是由 Blue Yonder 企業系統管理員在根企業層級建立。 它必須具有 API Access、用戶端系統管理員和 Store Manager 存取權。 建立連接時必須輸入帳戶和密碼。
- 您的 Blue Yonder WFM 環境中已啟用聯合 SSO 驗證。 請聯絡 Blue Yonder 支援人員，確認已啟用聯合 SSO。 他們需要下列資訊：

    - federatedSSOValidationService： `https://wfmconnector.teams.microsoft.com/api/v1/fedauth/{tenantId}/6A51B888-FF44-4FEA-82E1-839401E9CD74/authorize` 其中 {tenantId} 是您的租使用者Id
     - proxyHeader：X-MS-AuthToken

- 至少有一個團隊已設定在 Teams。
- 您新增Microsoft 365系統帳戶做為團隊擁有者，加入所有您想要地圖的團隊。</br> [在 Microsoft 365中建立此Microsoft 365](/microsoft-365/admin/add-users/add-users)授權。 接著，將帳戶新增為團隊擁有者至所有您想要地圖的團隊。 同步從 Blue Yonder WFM 的 Shifts 變更時，Shifts 連接器會使用此帳戶。

    我們建議您特別為此建立帳戶，而不要使用您的使用者帳戶。