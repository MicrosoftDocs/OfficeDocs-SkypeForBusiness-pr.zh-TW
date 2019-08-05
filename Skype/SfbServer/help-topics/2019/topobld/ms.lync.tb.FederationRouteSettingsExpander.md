---
title: 同盟路由設定擴展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FederationRouteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 22aa11b8-80ba-4c6a-9396-d11166903066
ROBOTS: NOINDEX, NOFOLLOW
description: 若要設定網站同盟路由指派, 您必須先在 Edge 伺服器或 Edge 伺服器池中啟用同盟。 如果在 Edge 伺服器或池中沒有啟用同盟, 該網站的同盟路由指派設定將不會提供修改。
ms.openlocfilehash: 6e68bc7cb2f5a9f04e208dc2f27ce7724aa7e793
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192380"
---
# <a name="federation-route-settings-expander"></a>同盟路由設定擴展器
 
若要設定網站同盟路由指派, 您必須先在 Edge 伺服器或 Edge 伺服器池中啟用同盟。 如果在 Edge 伺服器或池中沒有啟用同盟, 該網站的同盟路由指派設定將不會提供修改。

如果已設定 Edge 伺服器或池中的同盟設定, 您可以設定下列選項: 
  
- **允許將同盟路由指派給所有網站**此設定會影響所有網站。 請確定您在此網站所設定的設定適用于所有網站。
    
- **啟用 SIP 同盟**選取此選項以啟用 SIP 同盟路由, 然後選取 Director 或 Edge 池做為同盟路由。
    
- **啟用 XMPP 同盟**選取此選項以啟用 XMPP 同盟路由, 然後選取 Director 或 Edge 池做為同盟路由。
- 
  > [!NOTE]
  > XMPP 閘道和 proxy 可在商務用 Skype Server 2015 中使用, 但商務用 Skype Server 2019 已不再支援。 如需詳細資訊, 請參閱[遷移 XMPP 同盟](../../../../SfBServer2019/migration/migrating-xmpp-federation.md)。
    

