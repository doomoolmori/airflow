 .. Licensed to the Apache Software Foundation (ASF) under one
    or more contributor license agreements.  See the NOTICE file
    distributed with this work for additional information
    regarding copyright ownership.  The ASF licenses this file
    to you under the Apache License, Version 2.0 (the
    "License"); you may not use this file except in compliance
    with the License.  You may obtain a copy of the License at

 ..   http://www.apache.org/licenses/LICENSE-2.0

 .. Unless required by applicable law or agreed to in writing,
    software distributed under the License is distributed on an
    "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
    KIND, either express or implied.  See the License for the
    specific language governing permissions and limitations
    under the License.

External Redis
--------------

When using the ``CeleryExecutor`` or the ``CeleryKubernetesExecutor``
the chart will by default create a redis Deployment/StatefulSet
alongside airflow. You can also use “your own” redis instance by
providing the ``data.brokerUrl`` (or ``data.borkerUrlSecretName``) value
directly:

.. code-block:: bash

   helm install airflow . \
       --namespace airflow \
       --set executor=CeleryExecutor \
       --set redis.enabled=false \
       --set data.brokerUrl=redis://redis-user:password@redis-host:6379/0
