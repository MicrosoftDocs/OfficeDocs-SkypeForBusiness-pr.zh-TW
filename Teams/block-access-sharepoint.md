---
title: 封鎖特定使用者對 SharePoint 的存取
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: Nigolc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何封鎖特定使用者對 SharePoint 的存取
ms.openlocfilehash: edcdb8286ff69557215a0e481b12e67b81f440fe
ms.sourcegitcommit: 3db7c450d3afbc1049e1016d51016442e5764634
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203836"
---
# <a name="block-access-to-sharepoint-for-specific-users"></a>封鎖特定使用者對 SharePoint 的存取

在 Microsoft 365 中對 SharePoint 套用任何條件式存取 (CA) 原則也會套用至 Teams。 但是，有些組織希望封鎖對 SharePoint 檔案的存取 (上載、下載、檢視、編輯、建立)，但允許其員工在未受管理的裝置上使用Teams 桌面、行動裝置和 web 用戶端。 根據 CA 原則規則，封鎖 SharePoint 也會導致封鎖 Teams。 本文將解釋如何克服這一限制，允許員工繼續使用 Teams，同時完全封鎖對存儲在 SharePoint 中的檔的存取。

> [!Note]
> 封鎖或限制對未受管理裝置的存取取決於 Azure AD 條件式存取原則。 深入了解[Azure AD 授權](https://azure.microsoft.com/pricing/details/active-directory/)。 有關 Azure AD 中條件式存取的概覽，請參閱 [Azure Active Directory 中的條件式存取](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)。 有關推薦的 SharePoint Online 存取原則的資訊，請參閱 [用於保護 SharePoint 網站和檔的原則建議](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies)。 如果限制未受管理裝置上的存取，則受管理裝置上的使用者必須使用其中一個[受支援的作業系統和流覽器組合](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference#client-apps-condition)，否則他們的存取權限也將受到限制。

您可以封鎖或限制存取：

- 組織中的使用者，或僅部分使用者或安全性群組。

- 組織中的所有網站或僅部分網站。

存取被封鎖時，使用者將看到一條錯誤消息。 封鎖存取有助於提供安全性並保護安全資料。 存取被封鎖時，使用者將看到一條錯誤消息。

1. 開啟 SharePoint 系統管理中心。

2. 展開 **[原則]** > **[存取原則]**。

3. 在 **[未受管理的裝置]** 區段中，選取 **[封鎖存取]**，然後選取 **[儲存]**。

   ![原則的 [未受管理的裝置] 區段](media/no-sharepoint-access1.png)

4. 開啟 [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) 入口網站並瀏覽至 **[條件式存取原則]**。

    您將看到 SharePoint 建立了新原則，與此範例類似：

    ![名為 [使用應用程式強制限制流覽器存取] 的新原則](media/no-sharepoint-access2.png)

5. 更新原則以僅針對特定使用者或組。

    ![醒目提示 [選取使用者] 區段的 SharePoint 系統管理中心。](media/no-sharepoint-access2b.png)

  > [!Note]
> 設定此原則將切斷您對 SharePoint 系統管理入口網站的存取權限。 我們建議您設定排除原則並選取全域管理員和 SharePoint 管理員。

6. 驗證是否僅選取 SharePoint 作為目標 [雲端應用程式]

    ![選取 Sharepoint 作為目標應用程式。](media/no-sharepoint-access3.png)

7. 更新 **[條件]** 以包括桌面用戶端。

    ![桌面和行動裝置醒目提示。](media/no-sharepoint-access4.png)

8. 確保已啟用 **授與存取權**

    ![已啟用授與存取權。](media/no-sharepoint-access5.png)

9. 請確保已啟用 **[使用應用程式強制限制]**。

10. 啟用策略並選取 **[儲存]**。

    ![已啟用應用程式強制限制。](media/no-sharepoint-access6.png)

若要測試您的原則，您需要從任何用戶端（如 Teams 桌面應用程式或商務用 OneDrive 同步處理用戶端）登出，然後重新登入以查看原則是否有效。 如果您的存取已被封鎖，您將在 Teams 中看到指出該項目可能不存在的訊息。

 ![「找不到項目」訊息。](media/access-denied-sharepoint.png)

在 Sharepoint 中，您將收到拒絕存取的訊息。

![拒絕存取訊息。](media/blocked-access-warning.png)

## <a name="related-topics"></a>相關主題

[在 SharePoint 中控制對未受管理裝置的存取](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)
