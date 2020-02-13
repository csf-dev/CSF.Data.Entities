This repository has been **archived** and merged into **[CSF.ORM](https://github.com/csf-dev/CSF.ORM)**.  Further development on this work can be found there.

*It was found that a number of repositories were so closely linked that they should be converted to a single repository, even though they are multiple separate NuGet packages.*

---

# CSF.Data.Entities
This small library contains types which ease the integration of [CSF.Entities] and [CSF.Data].

[CSF.Entities]: https://github.com/csf-dev/CSF.Entities/
[CSF.Data]: https://github.com/csf-dev/CSF.Data/

## IEntityData
`IEntityData` and its implementations `EntityData` and `IdentityGeneratingEntityData` provide access to an underlying data store. This is typically an ORM-backed database but it could equally be an in-memory data-store for testing scenarios. The API provided by this is similar to that of a repository, *although the name repository has intentionally been avoided*.  Please note that this service exposes a `Query<T>()` method which means that it is *not a true repository*.

If you wish to build a repository (which exposes methods returning `IReadOnlyCollection<T>` or `IReadOnlyList<T>` etc) then you may build them atop this data access service.

## `IQuery<T>` extension methods
This library contains extension methods for `IQuery<T>`, permitting generic type inference of the return type from a generic `IIdentity<T>` instance.

## `InMemoryQuery` extension methods
The library also contains extension methods for `InMemoryQuery`, automatically providing the appropriate identity value to the `Add` method.

## Open source license
All source files within this project are released as open source software,
under the terms of [the MIT license].

[the MIT license]: http://opensource.org/licenses/MIT

This software is distributed in the hope that it will be useful, but please
remember that:

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
