---
title: 移轉 XMPP 同盟
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 舊版本提供可延伸的訊息和顯示狀態通訊協定（XMPP）閘道，可以做為個別的伺服器角色部署，以允許與 XMPP 部署聯盟。 在商務用 Skype Server 2019 中 & 已過時，已不再提供 XMPP 功能。 如果您想要繼續使用 XMPP 功能，可在具有舊版版本的 coexitence 環境中 availed （商務用 Skype Server 2015/Lync Server 2013）。 XMPP 功能是以兩個部分安裝：作為執行于舊版 Edge Server 上的 XMPP proxy，以及舊版前端伺服器上執行的 XMPP 閘道。
ms.openlocfilehash: 71b6c213450f51ea4b3fe1f351e22dbb992ce8ca
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752645"
---
# <a name="migrating-xmpp-federation"></a>移轉 XMPP 同盟

舊版本提供可延伸的訊息和顯示狀態通訊協定（XMPP）閘道，可以做為個別的伺服器角色部署，以允許與 XMPP 部署聯盟。 在商務用 Skype Server 2019 中不再提供 XMPP 功能且已被取代。 如果您想要繼續使用 XMPP 功能，您可以在具有舊版的共存環境（商務用 Skype Server 2015 或 Lync Server 2013）上進行。 XMPP 功能是以兩個部分安裝：作為執行于舊版 Edge Server 上的 XMPP proxy，以及舊版前端伺服器上執行的 XMPP 閘道。 
  
從遷移的角度來看，想要使用 XMPP 功能的使用者應該保留在舊版伺服器中，而且不應該移至商務用 Skype Server 2019 集區，但繼續使用舊版的 XMPP 閘道。 只有當 XMPP 同盟協力廠商在商務用 Skype Server 2015 或 Lync Server 2013 中設定時，才可以這麼做。 如果您想要繼續使用 XMPP 功能，請勿將舊版 Edge Server 遷移至商務用 Skype Server 2019。 不過，您可以使用舊版 Edge Server （搭配 XMPP Proxy）和商務用 Skype 2019 Edge Server 的共存。
  

    

