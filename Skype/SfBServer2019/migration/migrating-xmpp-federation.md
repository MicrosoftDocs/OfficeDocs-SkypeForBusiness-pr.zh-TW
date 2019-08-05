---
title: 遷移 XMPP 同盟
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: '先前的版本提供了可擴展的訊息和目前狀態通訊協定 (XMPP) 閘道, 可將其部署為個別的伺服器角色, 以允許與 XMPP 部署進行聯盟。 在商務用 Skype Server 2019 中, & 不贊成使用 XMPP 功能。 如果您想要繼續使用 XMPP 功能, 可以使用舊版版本 (商務用 Skype Server 2015/Lync Server 2013) availed 在 coexitence 環境中。 XMPP 功能安裝在兩個部分中: 作為在舊版 Edge 伺服器上執行的 XMPP proxy, 以及在舊版前端伺服器上執行的 XMPP 閘道。'
ms.openlocfilehash: fd2b51af84133e28e9a4de035333b1a282d71d38
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193064"
---
# <a name="migrating-xmpp-federation"></a>遷移 XMPP 同盟

先前的版本提供了可擴展的訊息和目前狀態通訊協定 (XMPP) 閘道, 可將其部署為個別的伺服器角色, 以允許與 XMPP 部署進行聯盟。 XMPP 功能已不再提供, 且在商務用 Skype Server 2019 中已過時。 如果您想要繼續使用 XMPP 功能, 您可以在具有舊版環境 (商務用 Skype Server 2015 或 Lync Server 2013) 的共存環境中執行此動作。 XMPP 功能安裝在兩個部分中: 作為在舊版 Edge 伺服器上執行的 XMPP proxy, 以及在舊版前端伺服器上執行的 XMPP 閘道。 
  
從遷移的角度而言, 想要使用 XMPP 功能的使用者應該保留在舊版伺服器中, 而且不應該移至 [商務用 Skype Server 2019], 但仍需繼續使用舊版 XMPP 閘道。 只有在商務用 Skype Server 2015 或 Lync Server 2013 中設定 XMPP 聯盟夥伴時, 才能這麼做。 如果您想要繼續使用 XMPP 功能, 則不要將舊版 Edge 伺服器遷移到商務用 Skype Server 2019。 不過, 您可以將舊版 Edge 伺服器 (與 XMPP Proxy) 與商務用 Skype 2019 Edge 伺服器共存。
  

    

