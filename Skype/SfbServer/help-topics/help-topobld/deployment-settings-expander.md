---
title: 部署設定展開工具
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.DeploymentSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7220ec1f-38cb-4297-870e-591a832cd2f2
description: 您可以使用下列區段編輯現有部署的屬性：
ms.openlocfilehash: a49fe0872d83011c433d011e1bb5ce7a348f1bd2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106869"
---
# <a name="deployment-settings-expander"></a>部署設定展開工具

您可以使用下列區段編輯現有部署的屬性：

- SIP 網域

- 簡單 URL

- 中央管理伺服器

## <a name="sip-domain"></a>SIP 網域

若要編輯 [預設 SIP 網域]，請輸入新的網域名稱。

若要新增 [其他支援的 SIP 網域]，請輸入您需要新增的網域名稱的名稱。按一下 [新增]，以接受它成為新的工作階段初始通訊協定 (SIP) 網域名稱。

若要更新現有的其他 SIP 網域名稱，請選取網域名稱並在文字方塊中進行變更。按一下 [更新] 以接受變更。

若要移除已定義的其他 SIP 網域名稱，請選取網域名稱，然後按一下 [移除]。

當您在 [編輯內容] 頁面上完成所有變更時，按一下 [確定] 以儲存變更。按一下 [取消] 捨棄任何變更。

## <a name="simple-urls"></a>簡單 URL

若要修改或定義簡單 URL，您要決定三種簡單 URL 中要編輯或變更哪一種。您可以選擇電話存取 URL、會議 URL，以及系統管理存取 URL。

若要修改電話存取 URL 或會議 URL，請選取您需要變更的 URL。按一下 [編輯 URL]。接著編輯 URL，再按一下 [確定] 儲存 URL。按一下 [取消] 捨棄任何變更。

若要新增 URL，請按一下 [新增]。在 [新增簡單 URL] 對話方塊中，指定 URL 再按一下 [確定] 儲存 URL。如果您需要將新的 URL 設成作用中的 URL，請選取 [成為選取網域的作用中 URL]。按一下 [取消] 捨棄任何變更。

若要使不同的 URL 成為作用中 URL (由 URL 旁的綠色核取記號表示)，請選取 URL，然後按一下 [成為作用中]。

> [!NOTE]
> 每個 SIP 網域只能有一個作用中的 URL。

如果您需要移除 URL，請選取 URL，然後按一下 [移除]。

> [!CAUTION]
> 請仔細閱讀簡單 URL 設定對話方塊頁面上的資訊。移除會議 URL 會導致無法存取使用者已排程的會議。將新的會議 URL 設為作用中之後，請考慮保留先前的 URL。當您確定使用者不會再使用舊的會議 URL 時，就可以放心移除它。

若要編輯或變更系統管理存取 URL，請編輯項目。

當您在 [編輯內容] 頁面上完成所有變更時，按一下 [確定] 以儲存變更。按一下 [取消] 捨棄任何變更。

## <a name="central-management-server"></a>中央管理伺服器

中央管理伺服器的位置可以從一個已定義的前端集區變更到另一個已定義的前端集區。若要變更中央管理伺服器的位置，請從 [要安裝中央管理伺服器的前端伺服器] 下的下拉式清單中，選取前端集區。前端伺服器可以是 Enterprise Edition 前端集區或 Standard Edition 前端伺服器。

> [!IMPORTANT]
> 定義、發行及部署基礎結構的中央管理存放區之後，必須以外部程序將中央管理存放區重新放置到另一個前端，才能變更中央管理存放區的位置。

如需移動中央管理存放區的詳細資訊，請參閱 Windows PowerShell Cmdlet 參考中的 [Move-CsManagementServer](/powershell/module/skype/move-csmanagementserver?view=skype-ps) 。

## <a name="see-also"></a>另請參閱

如需定義和設定這些設定的詳細資訊，請參閱＜[Defining and Configuring the Topology](/previous-versions/office/lync-server-2013/lync-server-2013-defining-and-configuring-the-topology)＞。