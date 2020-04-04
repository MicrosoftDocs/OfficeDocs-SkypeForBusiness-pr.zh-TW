---
title: 管理 Microsoft 團隊中的來賓存取權
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
f1.keywords:
- NOCSH
description: 瞭解如何建立您的第一份團隊與頻道、快速使用中的應用程式、監視器使用量與意見反應，以及取得資源以規劃貴組織內的推出。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: fea5ab9eec355d77f19165253fe97ee8aeb725ca
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/03/2020
ms.locfileid: "43139242"
---
<a name="manage-guest-access-in-microsoft-teams"></a>管理 Microsoft 團隊中的來賓存取權
======================================

> [!IMPORTANT]
> 您可能需要等候 24 小時，變更才會生效。 

**來賓**是 Microsoft 團隊中的使用者類型，包括所有 Office 365 商務版 Premium、Office 365 企業版、Office 365 商務基本版和 Office 365 教育版訂閱。 您不需要額外的 Office 365 授權。 請參閱以下有關[來賓存取授權](#guest-access-licensing-limits)的詳細資訊。

[團隊訪客存取] 是租使用者層級設定，預設為關閉狀態。 如需如何開啟來賓存取的詳細資料，請參閱[開啟或關閉對團隊的來賓存取權](set-up-guests.md)，或使用[來賓存取檢查清單](guest-access-checklist.md)逐步引導您完成設定。

開啟來賓存取之後，您可以使用[管理組織的 [管理團隊設定](enable-features-office-365.md)] 中所述的控制項來設定來賓的設定，並在[轉至新的 Microsoft 團隊系統管理中心時管理團隊](manage-teams-skypeforbusiness-admin-center.md)。     
    
IT 管理員可以在租使用者層級新增來賓、設定及管理來賓使用者原則和許可權，以及拉入來賓使用者活動的報告。 這些控制項可在 [團隊管理中心] 中取得。 來賓使用者的內容和活動與 Office 365 的其他部分相容性和審核保護的行為低於相同。

小組擁有者可以邀請新的來賓，並將現有的目錄來賓使用者新增至團隊系統管理中心的小組。 在 [**團隊** > **管理團隊**] 頁面上識別來賓使用者，並針對**組織範圍的 [設定** > **來賓存取權**] 頁面上的來賓設定與頻道相關的功能。 [設定] 包括允許來賓建立、更新及刪除頻道，如下圖所示。

![團隊中的來賓許可權設定](media/manage-guest-access-image1.png)
  
您可以使用 Azure Active Directory （Azure AD）入口網站來管理來賓及其對 Office 365 和團隊資源的存取權。 團隊訪客存取可使用 Azure AD 企業對企業（B2B）共同作業功能做為基礎基礎結構，以儲存身分識別屬性、成員資格以及多重要素驗證設定等安全性原則資訊。 若要深入瞭解 Azure AD B2B，請參閱[什麼是 AZURE AD b2b 共同作業？](https://go.microsoft.com/fwlink/p/?linkid=853011)以及[AZURE Active Directory b2b 合作常見問題](https://go.microsoft.com/fwlink/p/?linkid=853020)。

> [!NOTE]
> Microsoft 團隊永遠會採用 Azure AD 外部設定，以允許或禁止來賓使用者新增至租使用者。 如需詳細資訊，請參閱[授權 Microsoft 團隊中的來賓存取](Teams-dependencies.md)。


## <a name="guest-access-licensing-limits"></a>來賓存取授許可權制

Teams 未限制您可以新增的來賓數量。 然而，可以新增至租用戶的來賓總數會依據您 Azure AD 授權的允許量而定，通常是每位授權使用者允許 5 位來賓。 如需詳細資訊，請參閱 [Azure AD B2B 共同作業授權](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)。

由於這些授許可權制（並將您的租使用者保持在最新狀態），因此您應該定期檢查來賓存取權，以找出有權存取不需要的使用者。 您可以使用 Azure AD 來建立群組成員或指派給應用程式的使用者的存取權審查。 建立週期性存取檢查可節省您的時間。 如果您需要例行查看有權存取應用程式或群組成員的使用者，您可以定義這些評論的頻率。 

您可以自行執行來賓存取權審查、要求客人審查自己的成員資格，或是要求應用程式擁有者或商業決策人來執行存取審查。 使用 Azure 入口網站執行來賓存取審查。 如需詳細資訊，請參閱[使用 AZURE AD access 評論管理來賓存取](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews)。

###  <a name="prerequisites-for-azure-ad-access-reviews"></a>Azure AD access 評論的先決條件

您可以在 Microsoft 企業行動 + 安全性，E5 隨附的高級 P2 版本的 Azure AD 中使用 Access 評論。 如需詳細資訊，請參閱[Azure Active Directory 版本](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)。 與此功能互動的每個使用者，只要建立評論、填寫評論或確認其存取權，就必須擁有授權。



## <a name="lag-time-for-guest-access-settings-to-take-effect"></a>[來賓存取設定] 生效的延後時間

針對 Azure Active Directory 中的來賓存取設定，您需要2-24 小時才能讓變更在您的 Office 365 組織中生效。 當使用者嘗試將來賓新增到其小組時，如果使用者看到「與您的系統管理員聯繫」的訊息，可能是因為來賓功能尚未開啟，或設定尚未生效。 如需設定來賓存取問題的相關說明，請參閱[疑難排解團隊中的來賓存取權](troubleshoot-guest-access.md)。

  
## <a name="external-access-federation-vs-guest-access"></a>外部存取 (同盟) 與來賓存取

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a>詳細資訊

如需使用 PowerShell 來管理來賓存取的相關資訊，請參閱[使用 powershell 控制對團隊的來賓存取權](guest-access-powershell.md)。


