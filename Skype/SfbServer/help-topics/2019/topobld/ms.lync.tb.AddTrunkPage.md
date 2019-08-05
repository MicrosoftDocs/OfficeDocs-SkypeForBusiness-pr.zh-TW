---
title: 定義新主幹
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
ROBOTS: NOINDEX, NOFOLLOW
description: '您可以提供下列資訊來定義新的會話初始通訊協定 (SIP) 主幹:'
ms.openlocfilehash: c6586f9da069c3a3fc149b086562592db113b31e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189505"
---
# <a name="define-a-new-trunk"></a><span data-ttu-id="eb3d4-103">定義新主幹</span><span class="sxs-lookup"><span data-stu-id="eb3d4-103">Define a New Trunk</span></span>

<span data-ttu-id="eb3d4-104">您可以提供下列資訊來定義新的會話初始通訊協定 (SIP) 主幹:</span><span class="sxs-lookup"><span data-stu-id="eb3d4-104">You define a new session initiation protocol (SIP) trunk by providing the following information:</span></span>

- <span data-ttu-id="eb3d4-105">**主幹名稱**: 拓撲中要識別此主幹的唯一名稱</span><span class="sxs-lookup"><span data-stu-id="eb3d4-105">**Trunk name**: unique name in your topology that will identify this trunk</span></span>

- <span data-ttu-id="eb3d4-106">**關聯的 PSTN 閘道**: 從清單中選取部署和已設定的 pstn 閘道</span><span class="sxs-lookup"><span data-stu-id="eb3d4-106">**Associated PSTN Gateway**: select a deployed and configured PSTN gateway in your deployment from the list</span></span>

- <span data-ttu-id="eb3d4-107">**Ip/PSTN 閘道的偵聽埠**: ip PBX 或 PSTN 閘道將接聽的埠。</span><span class="sxs-lookup"><span data-stu-id="eb3d4-107">**Listening port for the IP/PSTN gateway**: port that the IP-PBX or PSTN gateway will listen on.</span></span> <span data-ttu-id="eb3d4-108">在您部署中設定的所有其他中繼偵聽埠都必須是唯一的</span><span class="sxs-lookup"><span data-stu-id="eb3d4-108">Must be unique from all other trunk listening ports configured in your deployment</span></span>

- <span data-ttu-id="eb3d4-109">**SIP 傳輸通訊協定**: 從清單中選取 [TCP] 或 [TLS]</span><span class="sxs-lookup"><span data-stu-id="eb3d4-109">**SIP Transport Protocol**: select from the list either TCP or TLS</span></span>

- <span data-ttu-id="eb3d4-110">**關聯的中繼伺服器**: 從清單中選取在您的部署中部署並設定的中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="eb3d4-110">**Associated Mediation Server**: select from the list a Mediation Server that is deployed and configured in your deployment</span></span>

- <span data-ttu-id="eb3d4-111">**關聯的中繼伺服器埠**: 將埠值設定為等於此 SIP 幹線將使用之中繼伺服器的 TCP 或 TLS 埠值</span><span class="sxs-lookup"><span data-stu-id="eb3d4-111">**Associated Mediation Server port**: set the port value equal to the TCP or TLS port value of the Mediation Server that this SIP trunk will use</span></span>

## <a name="see-also"></a><span data-ttu-id="eb3d4-112">另請參閱</span><span class="sxs-lookup"><span data-stu-id="eb3d4-112">See also</span></span>

[<span data-ttu-id="eb3d4-113">商務用 Skype Server 中的 M:N 幹線</span><span class="sxs-lookup"><span data-stu-id="eb3d4-113">M:N trunk in Skype for Business Server</span></span>](../../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[<span data-ttu-id="eb3d4-114">如何實作 SIP 主幹？</span><span class="sxs-lookup"><span data-stu-id="eb3d4-114">How do I implement SIP trunking?</span></span>](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)
