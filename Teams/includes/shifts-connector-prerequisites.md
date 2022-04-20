---
author: LanaChin
ms.author: v-lanachin
ms.date: 03/31/2022
ms.topic: include
audience: admin
ms.service: msteams
ms.openlocfilehash: ab375a876eb62e5f41e5dd7cda3743d4010b95ff
ms.sourcegitcommit: bf0071417188b33fc23e2a420187da5024d4bd40
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/20/2022
ms.locfileid: "64593644"
---
開始之前，請確定您有下列先決條件：

- Blue Yonder WFM 版本 2020.3、2021.1 或 2021.2。

    > [!NOTE]
    > 如果您有 Blue Yonder WFM 2020.3 或 2021.1，請套用 2020.3.0.4 或 2021.1.0.3 修補程式。 此修補程式可修正使用者在 Shifts 中持續收到錯誤訊息的問題。 它也會修正導致使用者無法更新其在 Shifts 中的顯示狀態的問題。

- 您的 Blue Yonder WFM 服務帳戶名稱、密碼和服務 URL：

    - 同盟驗證 URL
    - Cookie 驗證 URL
    - 員工自助 URL
    - 零售網路 API URL
    - 網站管理員 API URL
    - 系統管理 API URL

    如果您沒有此資訊，請連絡 Blue Yonder 支援。 該帳戶是由 Blue Yonder 企業系統管理員在根企業層級建立。 它必須具有 API 存取權、用戶端系統管理員和 Microsoft Store Manager 存取權。 建立連線需要帳戶和密碼。
- 同盟 SSO 驗證會在您的 Blue Yonder WFM 環境中啟用。 連絡 Blue Yonder 支援，以確保已啟用同盟 SSO。 他們需要下列資訊：

    - 同盟SSOValidationService： `https://wfmconnector.teams.microsoft.com/api/v1/fedauth/{tenantId}/6A51B888-FF44-4FEA-82E1-839401E9CD74/authorize` 其中 {tenantId} 是您的 tenantId
     - proxyHeader：X-MS-AuthToken

- Teams中至少已設定一個團隊。
- 您已將Microsoft 365系統帳戶新增為您要對應的所有團隊的團隊擁有者。</br> [在 Microsoft 365 中建立此帳戶](/microsoft-365/admin/add-users/add-users)，並指派Microsoft 365授權。 然後，將帳戶新增為您要對應的所有團隊的團隊擁有者。 當同步處理 Blue Yonder WFM 的 Shifts 變更時，Shifts 連接器會使用此帳戶。

    建議您特別為此目的建立帳戶，不要使用您的使用者帳戶。