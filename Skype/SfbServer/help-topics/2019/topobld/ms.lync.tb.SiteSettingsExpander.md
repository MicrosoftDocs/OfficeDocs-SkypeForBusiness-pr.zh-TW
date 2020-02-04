---
title: Lync Server 網站設定展開工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.SiteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 940bd9c0-bfcf-4d15-a5c1-a09f1cd692b6
ROBOTS: NOINDEX, NOFOLLOW
description: 若要編輯現有網站的屬性，請執行下列動作：
ms.openlocfilehash: 20c74cd3842137df5dce35647bdb5ad28b89b4e0
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41687966"
---
# <a name="lync-server-site-settings-expander"></a>Lync Server 網站設定展開工具

若要編輯現有網站的屬性，請執行下列動作：



## <a name="site-properties"></a>網站屬性

在 [網站內容] 中，您可以變更或修改網站名稱（必要）、描述（選擇性）、城市（選擇性）、省/市/自治區（選擇性），以及國家/地區代碼（選用）。

如需網站內容的詳細資訊，請參閱[將分支網站新增到您的拓撲](https://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx)。

## <a name="federation-route-properties"></a>同盟路由屬性

若要設定網站同盟路由指派，您必須先在 Edge 伺服器或 Edge 伺服器池中啟用同盟。 如果在 Edge 伺服器或池中沒有啟用同盟，該網站的同盟路由指派設定將無法供修改。

如果已設定 Edge 伺服器或池中的同盟設定，請選取 [在網站層級**啟用**]。 然後從下拉式清單中選取 [邊緣] 或 [主管]，將其設為同盟路線。

> [!CAUTION]
> 此設定會影響所有網站。 請確定您在此網站所設定的設定適用于所有網站。

## <a name="see-also"></a>另請參閱

如需詳細資訊，請參閱[外部使用者存取的拓撲](https://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx)。


