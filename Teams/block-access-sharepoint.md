---
title: 封鎖特定使用者對 SharePoint 的存取權
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
description: 瞭解如何封鎖特定使用者對 SharePoint 的存取權
ms.openlocfilehash: edcdb8286ff69557215a0e481b12e67b81f440fe
ms.sourcegitcommit: 3db7c450d3afbc1049e1016d51016442e5764634
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203836"
---
# <a name="block-access-to-sharepoint-for-specific-users"></a>封鎖特定使用者對 SharePoint 的存取權

在 Microsoft 365 的 SharePoint 中，將任何條件式存取 (CA) 原則，也會套用至小組。 不過，某些組織想要封鎖 SharePoint 檔案的存取權 (上傳、下載、查看、編輯、建立) 但仍允許員工在未受管理的裝置上使用小組桌面、行動裝置和 web 用戶端。 在 CA 原則規則底下，封鎖 Sharepoint 也會導致封鎖小組。 本文說明如何解決這項限制，並允許員工繼續使用團隊，同時完全封鎖對儲存在 SharePoint 中的檔案的存取權。

> [!Note]
> 受管理的裝置上的封鎖或限制存取依賴于 Azure AD 條件式存取原則。 瞭解 [AZURE AD 授權](https://azure.microsoft.com/pricing/details/active-directory/)。 如需 Azure AD 中的條件式存取權概覽，請參閱 [Azure Active Directory 中的條件式存取](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)。 如需建議的 SharePoint Online 存取原則的相關資訊，請參閱 [保護 sharepoint 網站和檔案的原則建議](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies)。 如果您在未受管理的裝置上限制存取，受管理的裝置上的使用者必須使用其中一個 [受支援的作業系統和瀏覽器混合](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference#client-apps-condition)，否則它們也會有有限的存取權。

您可以封鎖或限制存取：

- 組織中的使用者或只有部分使用者或安全性群組。

- 組織中的所有網站或只在部分網站中。

當存取權封鎖時，使用者會看到錯誤訊息。 封鎖存取可協助提供安全性並保護安全的資料。 當存取權封鎖時，使用者會看到錯誤訊息。

1. 開啟 SharePoint 系統管理中心。

2. 展開 [**原則**  >  **存取原則**]。

3. 在 [ **未管理的裝置** ] 區段中，選取 [ **封鎖存取** ] 並選取 [ **儲存**]。

   ![原則的 [未受管理的裝置] 區段](media/no-sharepoint-access1.png)

4. 開啟 [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) 入口網站，然後流覽至 [ **條件式存取原則**]。

    您會看到 SharePoint 建立了一個類似這個範例的新原則：

    ![名為「使用 app 強制限制的瀏覽器存取」的新原則](media/no-sharepoint-access2.png)

5. 將原則更新為僅以特定使用者或群組為目標。

    ![[Sharepoint 系統管理中心] 醒目提示 [選取使用者] 區段。](media/no-sharepoint-access2b.png)

  > [!Note]
> 設定此原則將會切斷您對 SharePoint 系統管理入口網站的存取權。 建議您設定排除原則，並選取全域和 SharePoint 系統管理員。

6. 確認只選取 [SharePoint] 作為 [目標雲端] App

    ![已選取 [Sharepoint] 作為目標 app。](media/no-sharepoint-access3.png)

7. 更新 **條件** 以包含桌面用戶端。

    ![桌面和行動裝置 app 已醒目提示。](media/no-sharepoint-access4.png)

8. 確認已啟用 **[授與存取權** ]

    ![已啟用 [授與存取權]。](media/no-sharepoint-access5.png)

9. 請確定已啟用 [ **使用 app 強制性限制** ]。

10. 啟用您的原則，然後選取 [ **儲存**]。

    ![已啟用應用程式強制執行限制。](media/no-sharepoint-access6.png)

若要測試原則，您必須從任何用戶端（例如團隊桌面應用程式或商務用 OneDrive 同步處理用戶端）登出，然後再次登入，以查看原則是否正常運作。 如果您的存取權遭到封鎖，就會在小組中看到一則訊息，指出該專案可能不存在。

 ![[找不到專案] 訊息。](media/access-denied-sharepoint.png)

在 Sharepoint 中，您會收到「拒絕存取」的訊息。

![[拒絕存取] 訊息。](media/blocked-access-warning.png)

## <a name="related-topics"></a>相關主題

[在 SharePoint 中控制非託管裝置的存取權](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)
