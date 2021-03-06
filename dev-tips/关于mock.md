# 关于mock
## 一、什么是mock？
通俗来讲，在开发和测试过程中，由于环境不稳定或者协同开发的同事未完成等情况下，有些数据不容易构造或者不容易获取，就创建一个虚拟的对象或者数据样本，用来辅助开发或者测试工作。减轻了对于协同模块的依赖，使开发以及测试变得更加独立。

## 二、为什么要使用mock？
现在的很多项目，基本都是划分为一个个小模块进行的，各个模块相互依赖，需要协同进行。但是实际开发过程中，由于各种原因，某些模块在当下可能是不可用的，这就对耦合较高的协同模块会产生不良影响，而使用mock，制造模拟数据，可以减轻这种负面因素。

如下的一些场景，可以使用mock很大程度上减轻这些负面影响。
1. 所需要数据难以获取（比如后端接口没写好，异常、特殊场景的数据）：这些特殊情况和场景下，可能生成一段真实数据很浪费时间，或者当下做不到。而使用mock比真实数据方便很多，此时mock就相当于真实接口数据的替代品，辅助其他相关联模块的开发；
1. 前后端分离，并行开发：前后端商定好接口标准后，按照统一的标准进行同时开发，规避对互相的依赖，减少时间浪费；
1. 前后端分离中，对于某些特殊接口，可能不能实际执行，不然会对数据造成污染，此时可以mock一个返回数据，规避此情况，而又不影响实际开发；
1. 自动化测试：如果在自动化测试中，出现了第三方数据不稳定或者其他情况，会影响测试进度，以及不方便定位问题所在。此时如果利用mock技术，模拟一种其他模块都是正常的场景，专门测试当前模块，可以减轻这种异常情况的干扰，方便定位问题；并且可以自己创造各种不同的数据，方便覆盖测试的各种情况。

三、mock的优缺点分析
优点：
1. 将本模块通过mock隔离起来，避免因为其他模块的问题，导致自身模块出现异常；
1. 前后端分离式开发中，通过制定好的接口规范，并行开发，提高总体开发效率；
1. 测试过程中，所依赖的模块异常时，可以使用mock数据替代，不影响测试进度；
1. 对于一些难构建的数据，可以使用mock来模拟；

风险：
1. 测试的过程中，如果大量使用mock，会使mock测试的场景失去了真实性，可能会到接入真实数据的时候才会发现缺陷，会造成后续修复成本较高。
