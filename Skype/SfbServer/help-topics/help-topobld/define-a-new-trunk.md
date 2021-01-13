---
title: 定義新主幹
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
description: 您可以透過提供下列資訊來定義新的會話初始通訊協定 (SIP) 主幹：
ms.openlocfilehash: bbed07920bdeddb78217e435e8813c89231cdcc9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833043"
---
# <a name="define-a-new-trunk"></a><span data-ttu-id="86010-103">定義新主幹</span><span class="sxs-lookup"><span data-stu-id="86010-103">Define a New Trunk</span></span>

<span data-ttu-id="86010-104">您可以透過提供下列資訊來定義新的會話初始通訊協定 (SIP) 主幹：</span><span class="sxs-lookup"><span data-stu-id="86010-104">You define a new session initiation protocol (SIP) trunk by providing the following information:</span></span>

- <span data-ttu-id="86010-105">**主幹名稱**：您的拓撲中的唯一名稱，可識別此主幹</span><span class="sxs-lookup"><span data-stu-id="86010-105">**Trunk name**: unique name in your topology that will identify this trunk</span></span>

- <span data-ttu-id="86010-106">**關聯的 PSTN 閘道**：從清單中選取部署中已部署及設定的 pstn 閘道</span><span class="sxs-lookup"><span data-stu-id="86010-106">**Associated PSTN Gateway**: select a deployed and configured PSTN gateway in your deployment from the list</span></span>

- <span data-ttu-id="86010-107">**IP/PSTN 閘道的聆聽埠**： IP-PBX 或 PSTN 閘道將接聽的埠。</span><span class="sxs-lookup"><span data-stu-id="86010-107">**Listening port for the IP/PSTN gateway**: port that the IP-PBX or PSTN gateway will listen on.</span></span> <span data-ttu-id="86010-108">必須是部署中所設定之所有其他主幹偵聽埠的唯一</span><span class="sxs-lookup"><span data-stu-id="86010-108">Must be unique from all other trunk listening ports configured in your deployment</span></span>

- <span data-ttu-id="86010-109">**SIP 傳輸通訊協定**：從清單中選取 [TCP] 或 [TLS]</span><span class="sxs-lookup"><span data-stu-id="86010-109">**SIP Transport Protocol**: select from the list either TCP or TLS</span></span>

- <span data-ttu-id="86010-110">**關聯** 的轉送伺服器：從清單中選取部署中已部署及設定的轉送伺服器</span><span class="sxs-lookup"><span data-stu-id="86010-110">**Associated Mediation Server**: select from the list a Mediation Server that is deployed and configured in your deployment</span></span>

- <span data-ttu-id="86010-111">**關聯的轉送伺服器埠**：設定的埠值等於此 SIP 主幹將使用之轉送伺服器的 TCP 或 TLS 埠值。</span><span class="sxs-lookup"><span data-stu-id="86010-111">**Associated Mediation Server port**: set the port value equal to the TCP or TLS port value of the Mediation Server that this SIP trunk will use</span></span>

## <a name="see-also"></a><span data-ttu-id="86010-112">另請參閱</span><span class="sxs-lookup"><span data-stu-id="86010-112">See also</span></span>

[<span data-ttu-id="86010-113">在商務用 Skype Server 2015 中 M:N 主幹</span><span class="sxs-lookup"><span data-stu-id="86010-113">M:N trunk in Skype for Business Server 2015</span></span>](../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[<span data-ttu-id="86010-114">如何執行 SIP 主幹？</span><span class="sxs-lookup"><span data-stu-id="86010-114">How do I implement SIP trunking?</span></span>](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)
