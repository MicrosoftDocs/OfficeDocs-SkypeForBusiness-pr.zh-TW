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
ms.localizationpriority: medium
description: 舊版本提供了可延伸的訊息和顯示狀態通訊協定 (XMPP) 閘道，可部署為個別的伺服器角色，以允許與 XMPP 部署的聯盟。 商務用 Skype Server 2019 中 & 已被取代的 XMPP 功能已不再可用。 如果您想要繼續使用 XMPP 功能，可以在 coexitence 環境中 availed 舊版 (商務用 Skype Server 2015/Lync Server 2013) 。 XMPP 功能是以兩個部分安裝：作為執行于舊版 Edge Server 上的 XMPP proxy，以及舊版前端伺服器上執行的 XMPP 閘道。
ms.openlocfilehash: a0c3eeaa6218c6e3b3726f755adcca6083a9ac3f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580127"
---
# <a name="migrating-xmpp-federation"></a>移轉 XMPP 同盟

舊版本提供了可延伸的訊息和顯示狀態通訊協定 (XMPP) 閘道，可部署為個別的伺服器角色，以允許與 XMPP 部署的聯盟。 XMPP 功能已不再可用，且在商務用 Skype Server 2019 中已被取代。 如果您想要繼續使用 XMPP 功能，您可以在具有舊版版本 (商務用 Skype Server 2015 或 Lync Server 2013) 的共存環境中執行此動作。 XMPP 功能是以兩個部分安裝：作為執行于舊版 Edge Server 上的 XMPP proxy，以及舊版前端伺服器上執行的 XMPP 閘道。 
  
從遷移的角度來看，想要使用 XMPP 功能的使用者應該保留在舊版伺服器中，而且不應該移至商務用 Skype Server 2019 集區，但繼續使用舊版 XMPP 閘道。 只有在商務用 Skype Server 2015 或 Lync Server 2013 中設定 XMPP 同盟協力廠商時，才可以這麼做。 如果您想要繼續使用 XMPP 功能，請勿將舊版 Edge Server 遷移至商務用 Skype Server 2019。 不過，您可以使用舊版 Edge server (與 XMPP Proxy) 和商務用 Skype 2019 Edge server 共存。
  

    

