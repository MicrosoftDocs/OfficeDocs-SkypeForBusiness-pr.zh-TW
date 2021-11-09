---
title: Lync Server 網站設定展開工具
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.SiteSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 940bd9c0-bfcf-4d15-a5c1-a09f1cd692b6
description: 若要編輯現有網站的屬性，請執行下列操作：
ms.openlocfilehash: 57de87177fe8239df3f09792bf139a9acd37ca18
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60841285"
---
# <a name="lync-server-site-settings-expander"></a>Lync Server 網站設定展開工具

若要編輯現有網站的屬性，請執行下列操作：



## <a name="site-properties"></a>網站屬性

在 [網站內容] 中，您可以變更或修改網站名稱 (必要) 、描述 (選用) 、城市 (optional) 、省/直轄市 (optional) ，以及國家/地區碼 (optional) 。

如需網站屬性的詳細資訊，請參閱 [將分支網站新增至您的拓撲](/previous-versions/office/lync-server-2013/lync-server-2013-add-branch-sites-to-your-topology)。

## <a name="federation-route-properties"></a>同盟路由屬性

若要設定網站同盟路由指派，您必須先啟用 Edge Server 或 Edge Server 集區上的同盟。 如果 Edge Server 或集區上沒有啟用同盟，將無法修改網站的同盟路由指派設定。

如果已設定 Edge Server 或集區上的同盟設定，請在網站層級選取 [ **啟用** ]。 然後從下拉式清單中選取 Edge 或導演，以設定為同盟路由。

> [!CAUTION]
> 此設定會影響所有網站。 請確定您在此網站上設定的設定適用于所有網站。

## <a name="see-also"></a>另請參閱

如需詳細資訊，請參閱 [外部使用者存取的拓撲](/previous-versions/office/lync-server-2013/lync-server-2013-scenarios-for-external-user-access)。