---
title: '為貴組織淘汰Microsoft Teams 免費版 (傳統) '
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.reviewer: alyake
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-meetings
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.custom:
- Licensing
- admindeeplinkMAC
robots: noindex
description: 瞭解如何移除 Teams 免費版 (傳統) 授權，並為貴組織的使用者指派付費的 Teams 授權。
ms.openlocfilehash: 3015036d0656a80ac8440d2c193003cc7d67d9fc
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767664"
---
# <a name="retire-microsoft-teams-free-classic-for-your-organization"></a>為貴組織淘汰Microsoft Teams 免費版 (傳統) 

> [!NOTE]
> 如果您是 Teams Free (傳統) 使用者，您將無法在 2023 年 4 月中存取 Teams，除非您的 IT 系統管理員採取本文中的下列動作。

Microsoft 將于 2023 年 4 月中淘汰 **Microsoft Teams 免費版 (傳統)** 授權。

本文提供 IT 系統管理員如何淘汰其組織的 **Microsoft Teams 免費版 (傳統)** 授權，以及移至付費 Teams 授權的相關指示。

如果您沒有在 2023 年 4 月中之前將使用者的免費 Teams 授權移至已付費的 Teams 授權，您的使用者將無法存取 Teams。

若要完成此程式，您可以選擇下列兩種方法之一：

- [使用Microsoft 365 系統管理中心。](#use-microsoft-365-admin-center-to-replace-licenses)
- [使用 Microsoft PowerShell。](#use-microsoft-powershell-to-replace-licenses)

如果您的組織決定不移轉到付費的 Teams 授權，您可以從 Teams 匯出貴組織的內容。 如需如何匯出 Teams 內容的相關指示，請參閱 [使用 Microsoft Teams 匯出 API 匯出內容](/microsoftteams/export-teams-content)。

## <a name="use-microsoft-365-admin-center-to-replace-licenses"></a>使用 Microsoft 365 系統管理中心 取代授權

如果貴組織已指派少數使用者使用 **Teams Free (傳統)** 授權，建議您使用Microsoft 365 系統管理中心移除及指派授權。

### <a name="check-users-current-teams-licensing"></a>檢查使用者目前的 Teams 授權

1. 登入[Microsoft 365 系統管理中心](https://go.microsoft.com/fwlink/p/?linkid=2024339)。
1. 在左側功能表上，移至 [ **使用者** >，然後選取 [ [**作用中的使用者**](https://go.microsoft.com/fwlink/p/?linkid=834822) ] 以檢視指派給使用者的授權。
    1. **[授權**] 欄會 **在** 指派該授權的使用者旁顯示Microsoft Teams 免費版 (傳統) 。
1. 在左側功能表上，移至 [ **計費** >並選取 [**[授權**](https://go.microsoft.com/fwlink/p/?linkid=842264) ]，查看您是否有付費 Teams 授權。
    1. 如果您的組織有可用的授權，請跳至 [指派付費的 Teams 授權](#assign-paid-teams-licenses) ，以將這些授權指派給 **使用 Teams Free (傳統)** 授權的使用者。
1. 如果有的話，請判斷您需要購買的付費 Teams 授權數目。

### <a name="purchase-paid-teams-licenses"></a>購買付費 Teams 授權

1. 在 [Microsoft 365 系統管理中心](https://go.microsoft.com/fwlink/p/?linkid=2024339)中，移至 **[計費**>並選取 **[購買服務]**。
1. 選 **取 [檢視產品** ] 以檢視所有可用的授權。
1. 選取 **[通訊及共同作業** ] 類別篩選以查看 Teams 授權。
1. 選擇您想要取代 **Teams Free (傳統)** 的付費 Teams 授權。
    1. 我們建議使用最多 300 個基座的 [ **Teams 基本** 版授權](https://admin.microsoft.com/adminportal/home#/catalog/offer-details/microsoft-teams-essentials-aad-identity-/2D7C59AC-F814-43E0-8E8E-E4EA91A09CAF)。
    1. 如果您需要超過 300 個基座，建議您購買 [Microsoft 365 E1 授權](https://admin.microsoft.com/Adminportal/Home#/catalog/offer-details/office-365-e1/CF4A479A-2119-4EF2-83D1-37CF8460EADA)。
1. 輸入您要購買的授權數目，然後選擇帳單頻率。
1. 選取 **[購買]** 按鈕以完成購買程式。

#### <a name="purchase-licenses-in-the-admin-center-marketplace"></a>在系統管理中心市集購買授權

有些租使用者可以存取 Microsoft 365 系統管理中心 Marketplace。 針對這些租使用者，您將在市集購買授權。

1. 在 [[Microsoft 365 系統管理中心](https://go.microsoft.com/fwlink/p/?linkid=2024339)] 中，從左側功能表選取 **[市** 集]。
1. 選取 [ **所有產品] 索引** 標籤。
1. 選取 **[通訊及共同作業** ] 類別篩選以查看 Teams 授權。
1. 選擇您想要取代 **Teams Free (傳統)** 的付費 Teams 授權。
1. 輸入您要購買的授權數目，然後選擇帳單頻率。
1. 選取 **[購買]** 按鈕以完成購買程式。

### <a name="assign-paid-teams-licenses"></a>指派付費 Teams 授權

1. 當您準備好要取代 **Teams Free (傳統)** 授權時，請在Microsoft 365 系統管理中心中移至 **[使用者**  >  [**作用中的使用者]**](https://admin.microsoft.com/adminportal/home#/users)。
1. 選取 [授權] 欄中列出所有擁有 **Teams 免費版 (傳統)** **授權的** 使用者。
1. 在系統管理中心的頂端，選取 **[管理產品授權]** 選項。
1. 在右側窗格中，選取 **[取代]**。
    1. 選取 **[取代]** 選項需要重新選取您希望指派給這些使用者的所有授權。 如果您只選取新的付費 Teams 授權，那些使用者所指派的其他授權將會從使用者中移除，並以 Teams 授權取代。
    1. 如果您的使用者有不同的授權需求，請分批完成此程式，以避免使用者的授權不正確。
1. 在側邊窗格中，選擇新的付費 Teams 授權以及使用者應指派的任何其他授權，然後選取 [ **儲存變更]** 按鈕。

## <a name="use-microsoft-powershell-to-replace-licenses"></a>使用 Microsoft PowerShell 取代授權

如果貴組織有大量使用者指派 **Teams Free (傳統)** 授權，建議您使用 PowerShell 大量取消指派授權，並將授權指派給使用者。

完成此程式之前，您需要為指派 **Teams Free (傳統)** 授權的使用者提供付費的 Teams 授權。 若要購買這些使用者的授權，請參閱 [購買付費的 Teams 授權](#purchase-paid-teams-licenses)。

1. 將您的 Microsoft 365 租使用者連線到 [Microsoft Graph PowerShell SDK](/powershell/microsoftgraph/get-started)。
1. 開啟 Microsoft PowerShell 傳統型應用程式。
1. [設定圖形 API的使用者和組織許可權](/microsoft-365/enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell#use-the-microsoft-graph-powershell-sdk)。
1. [從使用者帳戶移除 **Teams 免費版 (傳統)** 授權](/microsoft-365/enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell#removing-licenses-from-user-accounts)。
1. [指派付費 Teams 授權給使用者](/microsoft-365/enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell#assigning-licenses-to-user-accounts)。

如需 Graph PowerShell SDK 程式的詳細資訊，請參閱 [使用 Microsoft Graph PowerShell SDK](/microsoft-365/enterprise/view-licenses-and-services-with-microsoft-365-powershell)。
