---
title: 管理 Microsoft 團隊中的來賓存取權
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/21/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: IT 管理員可以在租使用者層級新增來賓、設定及管理來賓使用者原則和許可權、決定哪些使用者可以邀請客人, 以及拉入來賓使用者活動的報告。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0d65060049204f13d32158ba6c21ee18917df154
ms.sourcegitcommit: ca1ac291ab6394f050b9b517d9f3906f3a970b04
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2019
ms.locfileid: "36184299"
---
<a name="manage-guest-access-in-microsoft-teams"></a>管理 Microsoft 團隊中的來賓存取權
======================================

**來賓**是 Microsoft 團隊中的使用者/授權類型, 包含在所有 Office 365 商務版 Premium、Office 365 企業版和 Office 365 教育版訂閱中。 不需要額外的 Office 365 授權。 [團隊訪客存取] 是租使用者層級設定, 預設為關閉狀態。 如需如何啟用來賓存取的詳細資料, 請參閱[開啟或關閉 Microsoft 團隊的來賓存取權](set-up-guests.md)。

開啟**來賓**使用者/授權類型之後, 您可以透過在組織中的 [[管理 Microsoft 團隊設定](enable-features-office-365.md)] 中所述的控制項來設定來賓的設定, 並在[轉換為新的 Microsoft 團隊期間管理團隊。系統管理中心](manage-teams-skypeforbusiness-admin-center.md)。     
    
IT 管理員可以在租使用者層級新增來賓、設定及管理來賓使用者原則和許可權, 以及拉入來賓使用者活動的報告。 您可以透過 Microsoft 團隊系統管理中心來使用這些控制項。 來賓使用者的內容和活動與 Office 365 的其他部分相容性和審核保護都是相同的。

小組擁有者可以邀請新的來賓, 並將現有的目錄來賓使用者新增至他們的小組。 團隊擁有者可以透過**團隊** > **管理團隊**來識別來賓使用者, 以及透過**整個組織的設定** > **來賓存取**來設定來賓的頻道相關功能, 包括允許來賓建立、更新及刪除頻道, 如下圖所示。

![團隊中的來賓許可權設定](media/manage-guest-access-image1.png)
  
您可以使用 Azure Active Directory (Azure AD) 入口網站來管理來賓及其對 Office 365 和團隊資源的存取權。 團隊訪客存取可使用 Azure AD 企業對企業 (B2B) 共同作業功能做為基礎基礎結構, 以儲存身分識別屬性、成員資格以及多重要素驗證設定等安全性原則資訊。 若要深入瞭解 Azure AD B2B, 請參閱[什麼是 AZURE AD b2b 共同作業？](https://go.microsoft.com/fwlink/p/?linkid=853011)以及[AZURE Active Directory b2b 合作常見問題](https://go.microsoft.com/fwlink/p/?linkid=853020)。

> [!NOTE]
> Microsoft 團隊永遠會採用 Azure AD 外部設定, 以允許或禁止來賓使用者新增至租使用者。 如需詳細資訊, 請參閱[授權 Microsoft 團隊中的來賓存取](Teams-dependencies.md)。
  
## <a name="guest-access-vs-external-access-federation"></a>來賓存取與外部存取 (同盟)

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="review-guest-access-periodically"></a>定期審查來賓存取權

在 [團隊] 中, 您可以為每個授權的使用者新增5個來賓。 由於這項限制, 或由於您想要將您的租使用者保持在最新狀態, 因此您應該定期檢查來賓存取權, 以找出有存取權並不需要的使用者。 您可以使用 Azure AD 來建立群組成員或指派給應用程式的使用者的存取權審查。 建立週期性存取檢查可節省您的時間。 如果您需要例行查看有權存取應用程式或群組成員的使用者, 您可以定義這些評論的頻率。 

您可以自行執行來賓存取權審查、要求客人審查自己的成員資格, 或是要求應用程式擁有者或商業決策人來執行存取審查。 您使用 Azure 入口網站來執行來賓存取審查。 如需詳細資訊, 請參閱[使用 AZURE AD access 評論管理來賓存取](https://docs.microsoft.com/en-us/azure/active-directory/governance/manage-guest-access-with-access-reviews)。

###  <a name="prerequisites"></a>先決條件

您可以在 Microsoft 企業行動 + 安全性, E5 隨附的高級 P2 版本的 Azure AD 中使用 Access 評論。 如需詳細資訊, 請參閱[Azure Active Directory 版本](https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/active-directory-whatis)。 與此功能互動的每個使用者, 只要建立評論、填寫評論或確認其存取權, 就必須擁有授權。

小組不會限制您可以新增的來賓數目。 不過, 可以新增到您租使用者的來賓總數, 就是根據 AAD 授權所允許的專案數目。 如需詳細資訊, 請參閱[AZURE AD B2B](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance)共同版授權。

## <a name="guest-access-latencies"></a>來賓存取延遲

來賓設定是在 Azure AD 中設定。 在您的 Office 365 組織中, 變更的時間必須是2小時到24小時才能生效。 當使用者嘗試將來賓新增到其小組時, 如果使用者看到「與您的系統管理員聯繫」的訊息, 可能是因為來賓功能尚未啟用或設定尚未生效。

## <a name="more-information"></a>其他資訊

如需使用 PowerShell 來管理來賓存取的相關資訊, 請參閱[使用 powershell 控制對團隊的來賓存取權](guest-access-powershell.md)。


